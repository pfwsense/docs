.. _api_plugins_firewall:

Firewall
~~~~~~~~

The firewall API plugin (**os-firewall**) offers a way for machine to machine interaction between custom applications and PFWsense, it can
easily be installed like any other plugin via :menuselection:`System --> Firmware --> Plugins`.

Although the plugin does contains a basic user interface (in :menuselection:`Firewall --> Automation`), it's mirely intended
as a reference and testbed. There's no relation to any of the rules being managed via the core system.

.. Tip::

    Use your browsers "inspect" feature to compare requests easily, the user interface in terms of communication is exactly the same
    as offered by the API . Rules not visible in the web interface (:menuselection:`Firewall --> Automation`) will not be returned by the API either.



.. csv-table:: Abstract [non-callable] (FilterBaseController.php) 
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","firewall","filter_base","apply","$rollback_revision=null"
    "``POST``","firewall","filter_base","cancelRollback","$rollback_revision"
    "``GET``","firewall","filter_base","get",""
    "``POST``","firewall","filter_base","revert","$revision"
    "``POST``","firewall","filter_base","savepoint",""
    "``POST``","firewall","filter_base","set",""

    "``<<uses>>``", "", "", "", "*model* `Filter.xml <https://github.com/pfwsense/plugins/blob/master/net/firewall/src/pfwsense/mvc/app/models/PFWsense/Firewall/Filter.xml>`__"

.. csv-table:: Resources (FilterController.php)  -- extends : FilterBaseController 
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","firewall","filter","addRule",""
    "``POST``","firewall","filter","delRule","$uuid"
    "``GET``","firewall","filter","getRule","$uuid=null"
    "``*``","firewall","filter","searchRule",""
    "``POST``","firewall","filter","setRule","$uuid"
    "``POST``","firewall","filter","toggleRule","$uuid,$enabled=null"

.. csv-table:: Resources (SourceNatController.php)  -- extends : FilterBaseController 
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","firewall","source_nat","addRule",""
    "``POST``","firewall","source_nat","delRule","$uuid"
    "``GET``","firewall","source_nat","getRule","$uuid=null"
    "``*``","firewall","source_nat","searchRule",""
    "``POST``","firewall","source_nat","setRule","$uuid"
    "``POST``","firewall","source_nat","toggleRule","$uuid,$enabled=null"



-----------------------
Concept
-----------------------

The firewall plugin injects rules in the standard PFWsense firewall while maintaining visibility on them in the
standard user interface.

We use our standard :code:`ApiMutableModelControllerBase` to allow crud operations on rule entries and offer a set of
specific actions to apply the new configuration.
Since firewall rules can be quite sensitive with a higher risk of lockout, we also support a rollback mechanism here,
which offers the ability to rollback this components changes.

.. blockdiag::
    :scale: 100%

    diagram init {
        savepoint [label = "savepoint()"];
        administration [label = "administration"];
        apply [label = "apply(savepoint)"];
        cancelRollback [label = "cancelRollback(sp)"];
        savepoint -> administration -> apply ;
        apply -> cancelRollback [label = ".. 60s", style = dashed];
    }


The diagram above contains the basic steps to change rules, apply and eventually rollback if not being able to access the machine again.
When calling :code:`savepoint()` a new config revision will be created and the timestamp will be returned for later use.
If the :code:`cancelRollback(savepoint)` is not called within 60 seconds, the firewall will rollback to the previous state
identified by the savepoint timestamp (if available).


.. Note::

    The examples in this document disable certificate validation, make sure when using this in a production environment to
    remove the :code:`verify=False` from the :code:`requests` calls

.. Tip::

    The number of versions kept can be configured as "backup count" in :menuselection:`System -> Configuration -> History`.
    This affectively determines within how many configuration changes you can still rollback, if the backup is removed, a rollback
    will keep the current state (do nothing).


-----------------------
Administration example
-----------------------

Administrative endpoints are pretty standard use of :code:`ApiMutableModelControllerBase`, the example below searches for
a rule named "PFWsense_fw_api_testrule_1", when not found one will be added otherwise it will print the internal uuid.
Inline you will find a brief description of the steps performed.


.. literalinclude:: firewall.sample_create.py
    :language: python
    :linenos:
    :caption: administrative_example.py


.. Tip::

      Since our model contains default values for most attributes, we only need to feed the changes if we would like to keep the
      defaults. In this case the TCP/IP version was IPv4 by default for example. In most cases one would like to set all relevant properties
      in case defaults change over time.

-----------------------
Apply / revert example
-----------------------

This example will disable the rule created in the previous example and apply the changes using a savepoint, since we're not
calling :code:`cancelRollback(savepoint)` it will revert after 60 seconds to the original state.


.. literalinclude:: firewall.savepoint.py
    :language: python
    :linenos:
    :caption: savepoint_example.py


.. Note::

    The savepoint will only revert this components changes, other changes won't be affected by this revert, for example
    add an additional interface between savepoint and revert won't be affected.
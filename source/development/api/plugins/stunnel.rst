Stunnel
~~~~~~~

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","stunnel","service","reconfigure",""
    "``POST``","stunnel","service","restart",""
    "``POST``","stunnel","service","start",""
    "``GET``","stunnel","service","status",""
    "``POST``","stunnel","service","stop",""

    "``<<uses>>``", "", "", "", "*model* `Stunnel.xml <https://github.com/pfwsense/plugins/blob/master/security/stunnel/src/pfwsense/mvc/app/models/PFWsense/Stunnel/Stunnel.xml>`__"

.. csv-table:: Service (ServicesController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","stunnel","services","addItem",""
    "``POST``","stunnel","services","delItem","$uuid"
    "``GET``","stunnel","services","get",""
    "``GET``","stunnel","services","get",""
    "``GET``","stunnel","services","getItem","$uuid=null"
    "``*``","stunnel","services","searchItem",""
    "``POST``","stunnel","services","set",""
    "``POST``","stunnel","services","setItem","$uuid"
    "``POST``","stunnel","services","toggleItem","$uuid,$enabled=null"

    "``<<uses>>``", "", "", "", "*model* `Stunnel.xml <https://github.com/pfwsense/plugins/blob/master/security/stunnel/src/pfwsense/mvc/app/models/PFWsense/Stunnel/Stunnel.xml>`__"

Lldpd
~~~~~

.. csv-table:: Service (GeneralController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","lldpd","general","get",""
    "``GET``","lldpd","general","set",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/net-mgmt/lldpd/src/pfwsense/mvc/app/models/PFWsense/Lldpd/General.xml>`__"

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","lldpd","service","neighbor",""
    "``GET``","lldpd","service","reconfigure",""
    "``GET``","lldpd","service","restart",""
    "``GET``","lldpd","service","start",""
    "``GET``","lldpd","service","status",""
    "``GET``","lldpd","service","stop",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/net-mgmt/lldpd/src/pfwsense/mvc/app/models/PFWsense/Lldpd/General.xml>`__"

Tftp
~~~~

.. csv-table:: Service (GeneralController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","tftp","general","get",""
    "``POST``","tftp","general","set",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/ftp/tftp/src/pfwsense/mvc/app/models/PFWsense/Tftp/General.xml>`__"

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","tftp","service","reconfigure",""
    "``POST``","tftp","service","restart",""
    "``POST``","tftp","service","start",""
    "``GET``","tftp","service","status",""
    "``POST``","tftp","service","stop",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/ftp/tftp/src/pfwsense/mvc/app/models/PFWsense/Tftp/General.xml>`__"

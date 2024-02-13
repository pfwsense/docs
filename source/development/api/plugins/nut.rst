Nut
~~~

.. csv-table:: Resources (DiagnosticsController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","nut","diagnostics","upsstatus",""

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","nut","service","reconfigure",""
    "``POST``","nut","service","restart",""
    "``POST``","nut","service","start",""
    "``GET``","nut","service","status",""
    "``POST``","nut","service","stop",""

    "``<<uses>>``", "", "", "", "*model* `Nut.xml <https://github.com/pfwsense/plugins/blob/master/sysutils/nut/src/pfwsense/mvc/app/models/PFWsense/Nut/Nut.xml>`__"

.. csv-table:: Service (SettingsController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","nut","settings","get",""
    "``POST``","nut","settings","set",""

    "``<<uses>>``", "", "", "", "*model* `Nut.xml <https://github.com/pfwsense/plugins/blob/master/sysutils/nut/src/pfwsense/mvc/app/models/PFWsense/Nut/Nut.xml>`__"

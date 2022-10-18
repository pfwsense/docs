Clamav
~~~~~~

.. csv-table:: Service (GeneralController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","clamav","general","get",""
    "``GET``","clamav","general","set",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/security/clamav/src/pfwsense/mvc/app/models/PFWsense/ClamAV/General.xml>`__"

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","clamav","service","freshclam",""
    "``GET``","clamav","service","reconfigure",""
    "``GET``","clamav","service","restart",""
    "``GET``","clamav","service","start",""
    "``GET``","clamav","service","status",""
    "``GET``","clamav","service","stop",""
    "``GET``","clamav","service","version",""

    "``<<uses>>``", "", "", "", "*model* `General.xml <https://github.com/pfwsense/plugins/blob/master/security/clamav/src/pfwsense/mvc/app/models/PFWsense/ClamAV/General.xml>`__"

.. csv-table:: Resources (UrlController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","clamav","url","addUrl",""
    "``POST``","clamav","url","delUrl","$uuid"
    "``GET``","clamav","url","get",""
    "``GET``","clamav","url","getUrl","$uuid=null"
    "``*``","clamav","url","searchUrl",""
    "``GET``","clamav","url","set",""
    "``POST``","clamav","url","setUrl","$uuid"
    "``POST``","clamav","url","toggleUrl","$uuid"

    "``<<uses>>``", "", "", "", "*model* `Url.xml <https://github.com/pfwsense/plugins/blob/master/security/clamav/src/pfwsense/mvc/app/models/PFWsense/ClamAV/Url.xml>`__"

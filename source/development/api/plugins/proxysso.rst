Proxysso
~~~~~~~~

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","proxysso","service","createkeytab",""
    "``GET``","proxysso","service","deletekeytab",""
    "``GET``","proxysso","service","getCheckList",""
    "``GET``","proxysso","service","showkeytab",""
    "``POST``","proxysso","service","testkerblogin",""

.. csv-table:: Service (SettingsController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","proxysso","settings","get",""
    "``POST``","proxysso","settings","set",""

    "``<<uses>>``", "", "", "", "*model* `ProxySSO.xml <https://github.com/pfwsense/plugins/blob/master/www/web-proxy-sso/src/pfwsense/mvc/app/models/PFWsense/ProxySSO/ProxySSO.xml>`__"

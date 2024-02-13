Qemuguestagent
~~~~~~~~~~~~~~

.. csv-table:: Service (ServiceController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``POST``","qemuguestagent","service","reconfigure",""
    "``POST``","qemuguestagent","service","restart",""
    "``POST``","qemuguestagent","service","start",""
    "``GET``","qemuguestagent","service","status",""
    "``POST``","qemuguestagent","service","stop",""

    "``<<uses>>``", "", "", "", "*model* `QemuGuestAgent.xml <https://github.com/pfwsense/plugins/blob/master/emulators/qemu-guest-agent/src/pfwsense/mvc/app/models/PFWsense/QemuGuestAgent/QemuGuestAgent.xml>`__"

.. csv-table:: Service (SettingsController.php)
   :header: "Method", "Module", "Controller", "Command", "Parameters"
   :widths: 4, 15, 15, 30, 40

    "``GET``","qemuguestagent","settings","get",""
    "``POST``","qemuguestagent","settings","set",""

    "``<<uses>>``", "", "", "", "*model* `QemuGuestAgent.xml <https://github.com/pfwsense/plugins/blob/master/emulators/qemu-guest-agent/src/pfwsense/mvc/app/models/PFWsense/QemuGuestAgent/QemuGuestAgent.xml>`__"

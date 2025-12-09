# App Packaging Instructables – Manifest Schema (v0.9)

This schema defines the **common JSON format** used for documenting silent install patterns,
uninstall commands, detection hints, and other packaging knowledge related to enterprise software.
The intent is **accuracy when possible** and **honest inference when necessary**.

This format does **not guarantee correctness**, and all values should be tested in a lab or pilot environment before deployment.

---

## Top-Level Structure

```jsonc
{
  "id": "vendor.product.version",
  "name": "Software Name",
  "version": "2023",
  "publisher": "It does matter",
  "description": "Silent install notes, uninstall commands, caveats, etc.",

  "source": {
    "type": "installer",                  // installer, script, unknown, some have multiple
    "relativePath": "Installer.exe"
  },

  "installer": {
    "type": "exe",                         // exe, msi, bat, ps1, unknown
    "silentArgs": "-i deploy -q ...",
    "uninstallCmd": "C:\\Program Files\\Program\\...\\Installer.exe -i uninstall",
    "installOrder": [
      "CONNECTION Client"
    ]
  },

  "detection": {
    "type": "uninstallReg",                // uninstallReg, file, productCode, script, unknown
    "keyPath": "HKLM\\...",
    "valueName": "DisplayName",
    "operator": "contains",
    "expectedValue": "vendor product version"
  },

  "prerequisites": [
    "Visual C++ Redistributable",
    "Client"
  ],

  "variables": {
    "collectionFile": "Collection.xml"
  },

  "caveats": [
    "BundleManifest GUID may differ by edition",
    "Folder name inferred from year"
  ],

  "review": {
    "reviewed": false,                    // true only after actual validation
    "reviewedBy": null,
    "reviewedDate": null
  },

  "origin": {
    "type": "seed|generated|user",
    "providedBy": "WebVG"
  }
}

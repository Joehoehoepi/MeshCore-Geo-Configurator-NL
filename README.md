# MeshCore Geo Configurator by Infinity

🌐 **Overview**

The **MeshCore Geo Configurator** is a professional-grade utility designed for the Dutch MeshCore community. It streamlines the configuration of regional settings for LoRa/Mesh nodes by providing an intuitive, map-based interface to generate precise CLI commands.

🎯 **The "Triple-Border" Challenge**

This tool was specifically developed to solve the complexity of nodes located near provincial borders.

Take **Elburg** as a prime example:
If you set a coverage radius of 10 kilometers around Elburg, your signal crosses into **three different provinces**:

* **Gelderland** (Home province)
* **Flevoland** (Just across the water)
* **Overijssel** (Neighboring to the Northeast)

**The Risk:** Without this configurator, a user might only configure their home province/region, causing the node to become "isolated" from peers that are physically nearby but across a provincial line. This tool ensures **100% cross-border connectivity** by automatically identifying every relevant municipality.

🚀 **Key Features**

* **Complete Dutch Database:** Includes all **342 municipalities** with accurate coordinates and provincial coding.
* **Dynamic Radius Selection:** Adjust your reach (5km to 40km) to match your antenna's performance.
* **Smart Cross-Border Detection:** Automatically identifies and maps all municipalities within your reach, regardless of provincial borders.
* **Full Command Hierarchy:** Generates the correct `region put` and `region allowf` commands for:
1. **Country** (NL)
2. **Provinces** (e.g., nl-ge, nl-fl)
3. **Municipalities** (e.g., nl-ge-elb, nl-fl-dro)


* **Single-File Portability:** A "zero-dependency" HTML tool that runs in any browser without installation.

🛠 **How to Use**

1. **Launch:** Open the `index.html` file in any modern web browser.
2. **Set Range:** Use the slider to set your desired coverage radius (in kilometers).
3. **Locate:** Click on your node's exact location on the map.
4. **Copy:** Click the **⚡ COPY CONFIGURATION** button to grab the generated CLI block.
5. **Apply:** Paste the commands directly into your MeshCore CLI and you're done.

📋 **Example CLI Output**

For a border area, the tool calculates the required logic instantly:

```bash
region put nl
region put nl-ge nl
region put nl-fl nl
region put nl-ge-elb elb
region put nl-fl-dro dro
region allowf nl
region allowf nl-ge
...
region save

```

🔒 **Integrity & Security**

This edition uses **JavaScript Obfuscation** to protect the internal municipal database and logic from accidental tampering. This ensures the tool remains a reliable, "single-source-of-truth" for the community while remaining easy to distribute.

---

*Created by Infinity — Strengthening the Mesh network, one node at a time.*

---

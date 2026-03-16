# MeshCore Geo Configurator by Infinity

## 🌐 Overview

The **MeshCore Geo Configurator** is a specialized tool designed for the Dutch MeshCore community. It simplifies the process of configuring regional settings for LoRa/Mesh nodes by providing a visual, map-based interface to generate the necessary CLI commands.

## 🎯 The Problem: The "Triple-Border" Challenge

One of the main reasons this tool was developed is to solve the complexity of nodes located near provincial borders.

Take **Elburg** as a prime example. If you set a coverage radius of just 10 kilometers around Elburg, you are immediately dealing with three different provinces:

1. **Gelderland** (where Elburg is located)
2. **Flevoland** (just across the water)
3. **Overijssel** (neighboring to the Northeast)

**The Issue:**
Without this configurator, a user would manually have to find the specific codes for every municipality in those three provinces. If a user only configures their home province, the node might become "isolated" from nearby peers that are physically close but happen to be across a provincial line.

## 🚀 Key Features

* **Dynamic Radius Selection:** Easily adjust your reach from 20km to 60km.
* **Smart Cross-Border Detection:** Automatically identifies all municipalities within your reach, regardless of provincial borders.
* **Automatic Hierarchy:** Generates the correct `region put` and `region allowf` commands for the Country (NL), the Provinces, and the specific Municipalities.
* **Infinity Secure Edition:** Includes code obfuscation to protect the integrity of the data structure while remaining a portable HTML tool.

## 🛠 How to Use

1. Open the `configurator.html` file in any modern web browser.
2. Use the slider to set your desired diameter (range).
3. Click on your node's location on the map.
4. Copy the generated code block from the dark console window.
5. Paste the commands directly into your MeshCore CLI.

## 📋 Example CLI Output

When clicking near a border area, the tool instantly calculates the required logic:

```bash
region put nl
region put nl-ge nl
region put nl-fl nl
region put nl-ge-elb nl-ge
region put nl-fl-dro nl-fl
... (and so on)
region save

```

## 🔒 Security

This version uses **JavaScript Obfuscation** to ensure that the underlying municipal database and logic are protected from accidental tampering, while maintaining a single-file "zero-dependency" portability.

---

*Created by Infinity - Strengthening the Mesh network, one node at a time.*

---

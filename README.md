# SubMerge

### Unified Subdomain Recon & Deduplication Tool

*A Bash-based automation script for subdomain enumeration and consolidation.*

---
<img width="592" height="640" alt="image" src="https://github.com/user-attachments/assets/ea6e8aa9-a26c-4b69-bf16-6744ebd8dd00" />


---

## 🚀 Overview

**SubMerge** is a lightweight yet powerful **recon automation tool** designed to gather subdomains from multiple popular recon utilities—both built into Kali Linux and those installed externally from GitHub repositories.
It aggregates results from tools like **Subfinder**, **Amass**, and **Assetfinder**, merges their output, removes duplicates, and produces a single, clean `unique_subdomains.txt` file ready for further reconnaissance or scanning.

Think of SubMerge as your **“collector & cleaner”** for subdomains — automating the first stage of your bug bounty or reconnaissance workflow.

---

## ⚙️ Features

* 🧩 Combines output from multiple enumeration tools.
* 🧹 Automatically removes duplicates.
* 💾 Saves results neatly into a single output file.
* ⚡ Built in **pure Bash** – no complex setup.
* 🔍 Easy to extend or modify for your recon workflow.

---

## 🧰 Requirements

Before running SubMerge, make sure the required tools are installed.
All dependencies are included in the provided `requirements.txt`.

To install them all at once:

```bash
sudo apt update
pip install -r requirements.txt --break-system-packages
```

> 💡 If `--break-system-packages` gives errors on Kali, use a Python virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

## 🪄 Installation

Clone the repository and give execution permission:

```bash
git clone https://github.com/Cyberparth/SubMerge.git
cd SubMerge
chmod +x submerge.sh
```

---

## 🧑‍💻 Usage

Run SubMerge with a domain name of your choice:

```bash
./submerge.sh example.com
```

The tool will:

1. Enumerate subdomains using **Subfinder**, **Amass**, **Assetfinder**, and more.
2. Merge all results into one file.
3. Deduplicate entries.
4. Save final output as:

   ```
   /output/unique_subdomains.txt
   ```

---

## 📂 Output Example

```
sub1.example.com
api.example.com
dev.example.com
test.example.com
```

---

## 🧩 Supported Tools

SubMerge currently integrates the following:

* Subfinder
* Amass
* Assetfinder
* Findomain *(optional)*
* Other future tools (configurable in script)

---

## 🛠️ Customization

You can modify the script to:

* Add new enumeration tools
* Change output directory
* Chain with scanners like `httpx`, `nuclei`, or `dalfox`

---

## ⚠️ Disclaimer

This tool is intended **for educational and authorized security testing only.**
Unauthorized scanning or reconnaissance is strictly prohibited.

---

## 🧑‍💻 Author

**CyberParth** — [GitHub Profile](https://github.com/Cyberparth)

---

Would you like me to make the **README visually themed** like the “ReconNEX” example (with ASCII logo + color bash output + fancy structure)?
I can generate that version next.


# 🕵️‍♂️ REDACT — Privacy-First Redaction Chrome Extension

![FastAPI](https://img.shields.io/badge/backend-FastAPI-009688?logo=fastapi)
![Python](https://img.shields.io/badge/python-3.10%2B-blue?logo=python)
![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)
![Platform](https://img.shields.io/badge/platform-Chromium%20Extension-yellow?logo=googlechrome)

**REDACT** is a secure and easy-to-use Chrome Extension that performs redaction, masking, and anonymization of sensitive data—particularly Personally Identifiable Information (PII)—from documents. Built for privacy, it supports PDFs, images, and Word documents directly from your browser using a FastAPI Python backend.
## 🧠 System Architecture

```text
+-------------------------+         +--------------------------+
|     Chrome Extension    |         |   FastAPI Python Backend |
| (popup.html + popup.js) |         |      (Uvicorn server)    |
+------------+------------+         +------------+-------------+
             |                                |
             |  POST file + type + level      |
             |------------------------------->|
             |                                |
             |      com.py dispatches         |
             |    to PDF/Image/DOC script     |
             |                                |
             |  <----- Returns redacted file  |
             |                                |
+------------v------------+         +------------v-------------+
|   Download Redacted     |         |     Temp Files Auto      |
|      File (Blob)        |         |        Deleted           |
+-------------------------+         +--------------------------+
````

---

## 🚀 Features

* 🔐 **PII Protection**: Redact names, phone numbers, emails, faces, and more
* 📄 **File Support**: PDFs, images (JPG/PNG), DOCX (Word); more coming soon
* 🌐 **Chrome Native**: No need to leave the browser
* ⚡ **FastAPI Backend**: Ultra-light, async processing using Python
* 🧹 **Ephemeral Storage**: Files are deleted after processing
* 🧠 **Smart Redaction**: Configurable redaction level (e.g. 25%, 50%, 75%, 100%)
* 🔓 **Open Access**: No login, no tracking

---

## 📤 Upload Flow

1. Select a file using the extension popup
2. Choose redaction **level** (0% → 100%)
3. Choose redaction **type** (e.g. blackout, blur, synthetic)
4. Click **Redact**
5. A redacted version will be downloaded instantly

---



## 🛠 Tech Stack

| Layer     | Technology                    |
| --------- | ----------------------------- |
| Frontend  | HTML, CSS, JavaScript (MV3)   |
| Backend   | Python 3.10, FastAPI, Uvicorn |
| Redaction | OpenCV, spaCy, PyMuPDF, etc.  |
| Packaging | Docker                        |
| Storage   | Ephemeral + tempfile-based    |

---

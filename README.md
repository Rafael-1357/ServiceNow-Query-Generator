# ServiceNow Query Generator

[![Português](https://img.shields.io/badge/🇧🇷-LEIA_EM_PORTUGUÊS-brightgreen)](./README.pt-br.md)

**ServiceNow Query Generator** is a lightweight, zero-dependency static HTML widget designed to be embedded via Iframe (e.g., in SharePoint or internal portals).

It allows users to input a single search term (like an Asset Tag or CI Name) and generates a complex, multi-variable query link that performs a "dot-walk" search across multiple reference fields in ServiceNow.

### 🔐 Security & Privacy by Design

This project is designed to be hosted publicly on GitHub without leaking sensitive corporate information.

* **Agnostic Codebase:** The HTML/JS file contains zero hardcoded hostnames, instance names, or internal variable IDs.
* **URL Configuration:** All configuration happens via parameters passed to the Iframe URL at runtime.

## ✨ Key Features

* **🌐 Internationalization (i18n):** Built-in support for English (default) and Portuguese (pt-BR), switchable via URL parameter.
* **🚀 Zero Dependencies:** A single HTML file that runs anywhere. No build steps, no Node.js required.
* **🎨 Fully Customizable UI:** Change titles, labels, button text, hints, and placeholders via URL.
* **🖼️ Embedded Logos:** Support for Base64 encoded images in the URL, allowing custom branding without external image hosting.
* **🔗 dual-Action:** Users can either open the query directly in a new tab or copy the generated link to the clipboard.

## 🛠️ Usage Guide

### 1. Deploy
Simply host the `index.html` file on any static web server (GitHub Pages, Netlify, internal server).

### 2. Configure the URL
Construct the URL to be used in your Iframe `src` attribute by appending the necessary parameters.

#### Required Parameters

| Parameter | Description | Example |
| :--- | :--- | :--- |
| `host` | The base URL of your ServiceNow instance. | `https://instance.service-now.com` |
| `ids` | A comma-separated list of the variable sys_ids to search against. | `e85466...cc,fc8850...cb` |

#### Customization Parameters (Optional)

| Parameter | Description | Default (EN) |
| :--- | :--- | :--- |
| `lang` | Language selection (`en` or `pt-BR`). | `en` |
| `title` | Main header title. | "Search Tool" |
| `subtitle`| Header subtitle. | "Corporate Search" |
| `label` | Input field label. | "Search Query" |
| `hint` | Helper text below input. | "Enter the text to search" |
| `logo` | URL or Base64 string for the header icon. | (Generic Search Icon) |
| `btnOpen` | Label for the open button. | "Search" |
| `btnCopy` | Label for the copy button. | "Copy" |

---

### 💡 Configuration Examples

#### Example 1: Basic English Setup
```text
https://your-username.github.io/servicenow-query-generator/index.html?host=https://dev12345.service-now.com&ids=id1,id2,id3&lang=en&subtitle=SNOW%20Tools
```

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

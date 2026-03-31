# 🌳 Family Tree

> A modern, interactive family tree web application built with **React 18** (CDN), vanilla CSS, and localStorage — zero build tools required.

![Family Tree Preview](docs/preview.png)

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage Guide](#usage-guide)
- [Tech Stack](#tech-stack)
- [Data Format](#data-format)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Family Tree is a **single-file React web app** that lets you build, edit, and visualise your family tree directly in the browser. No npm, no build step, no server — just open `index.html` in any browser or serve it via XAMPP/Apache.

---

## ✨ Features

| Feature                      | Details                                                     |
| ---------------------------- | ----------------------------------------------------------- |
| 🎨 **Modern UI**             | Dark glassmorphism design with gold & coral gradients       |
| 👨‍👩‍👧‍👦 **Multi-generation tree** | Renders generations with couple connectors and branch lines |
| ✏️ **Edit members**          | Update name, birth/death year, gender, role at any time     |
| 📷 **Photo upload**          | Click any avatar to swap a photo from your device           |
| 💑 **Add spouse**            | Attach a spouse to any single member                        |
| ➕ **Add children**          | Add children under any couple or individual                 |
| 🗑️ **Delete members**        | Removes member and auto-cleans all relationships            |
| 💾 **Auto-save**             | Changes persist automatically via `localStorage`            |
| 📂 **Import / Export**       | Save your tree as JSON; reload it any time                  |
| 🔄 **Reset**                 | One-click restore to the sample Anderson family             |

---

## 📁 Project Structure

```
FamilyTreeRoot/
│
├── index.html              # Main application (React + CSS + JS, all-in-one)
│
├── docs/
│   ├── preview.png         # Screenshot for README
│   └── data-schema.md      # JSON data format reference
│
├── samples/
│   └── sample-family.json  # Example family tree JSON for import
│
├── .gitignore              # Git ignore rules
├── LICENSE                 # MIT License
└── README.md               # This file
```

---

## 🚀 Getting Started

### Option 1 — XAMPP (recommended for local dev)

1. Clone or download this repository into your XAMPP `htdocs` folder:
   ```bash
   git clone https://github.com/Glenn-IT/FamilyTreeRoot.git C:/xampp/htdocs/FamilyTreeRoot
   ```
2. Start **Apache** in the XAMPP Control Panel.
3. Open your browser and go to:
   ```
   http://localhost/FamilyTreeRoot/
   ```

### Option 2 — Direct file open

1. Double-click `index.html` — it opens directly in your browser.
2. Note: photo uploads use `FileReader` (works without a server).

### Option 3 — Any static host

Deploy the `index.html` (and optionally the `docs/` and `samples/` folders) to:

- GitHub Pages
- Netlify / Vercel (drag & drop)
- Any Apache / Nginx server

---

## 📖 Usage Guide

### Adding a new family member

- Click **➕ Add Member** in the toolbar.
- Fill in the name, birth year, gender and role.
- Optionally upload a photo.
- Click **Save Member**.

### Editing an existing member

- Click the **✏️ pencil icon** on any card.
- Update any field and click **Save Member**.

### Uploading a photo

- Click directly on the **avatar** circle on any card, **or**
- Open the edit modal — the photo upload area is at the top.

### Adding a spouse

- Click **💑 + Spouse** next to any member who has no spouse yet.

### Adding a child

- Click the **➕ green icon** on the parent's card.
- Fill in the child's details and save.

### Import / Export

- **Export** — Click 💾 Export JSON to download your tree as `family-tree.json`.
- **Import** — Click 📂 Import JSON and select a previously exported file.

---

## 🛠 Tech Stack

| Technology       | Version      | Purpose                       |
| ---------------- | ------------ | ----------------------------- |
| React            | 18 (CDN)     | UI components & state         |
| ReactDOM         | 18 (CDN)     | DOM rendering                 |
| Babel Standalone | Latest (CDN) | JSX → JS in-browser transform |
| Playfair Display | Google Fonts | Elegant serif headings        |
| Inter            | Google Fonts | Clean UI body font            |
| localStorage     | Browser API  | Persistent data storage       |
| FileReader API   | Browser API  | Client-side image/JSON import |

> No npm, no webpack, no build step required.

---

## 🗂 Data Format

Each family member is stored as a JSON object. See [`docs/data-schema.md`](docs/data-schema.md) for full details.

**Quick example:**

```json
{
  "id": "p1",
  "firstName": "Robert",
  "lastName": "Anderson",
  "birth": "1935",
  "death": "2010",
  "gender": "male",
  "role": "patriarch",
  "photo": null,
  "spouseId": "p2",
  "parentIds": [],
  "childrenIds": ["p3"]
}
```

---

## 🗺 Roadmap

- [ ] Drag-and-drop reordering of members
- [ ] SVG connector lines between generations
- [ ] Search / filter members by name
- [ ] Print / PDF export
- [ ] Multiple family tree tabs
- [ ] Dark / light theme toggle
- [ ] Mobile swipe navigation
- [ ] Shareable link via URL hash

---

## 🤝 Contributing

Contributions, issues and feature requests are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Commit your changes: `git commit -m 'Add my feature'`
4. Push the branch: `git push origin feature/my-feature`
5. Open a **Pull Request**

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">Made with ❤️ by <a href="https://github.com/Glenn-IT">Glenn-IT</a></p>

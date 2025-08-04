# Laravel Project Tracker 🧭
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive and extensible **Python-based static analysis tool** for Laravel applications. This tool scans a Laravel project directory and produces a detailed, cross-referenced **Excel report with up to 36 structured sheets**, helping developers, QA teams, and auditors understand the full architecture of a Laravel project.

---

## 🚀 What It Does

Laravel projects often become complex, with deep interconnections between routes, controllers, models, views, and other components. This tool automatically parses your Laravel project and:

- Detects and categorizes key components (routes, models, controllers, views, configs, etc.)
- Maps internal relationships between components
- Highlights missing links, validation gaps, and security concerns
- Produces an **interactive Excel report** for inspection, QA, and documentation

---

## 📑 Excel Report Overview

The generated Excel file (`laravel_project_tracker.xlsx`) includes **up to 36 hyperlinked sheets**, grouped as follows:

### 🔖 Overview
- **TOC** – Table of contents with sheet names, entry counts, and clickable links
- **Dashboard** – Summary stats (routes, views, models, etc.) and project metrics

### 🌐 Routing
- **Web Routes** – All routes from `routes/web.php`
- **API Routes** – All routes from `routes/api.php`
- **Route References** – Where routes are used in code (JS, views, tests, etc.)

### 🧠 Controllers & Views
- **Controllers** – List of controllers, with method-level model/view references
- **Views** – All Blade templates with route usage and embedded components
- **Blade Hierarchy** – `@extends` / `@include` relationships mapped as a tree
- **Livewire Components** – Blade and PHP-level Livewire usage

### 📦 Models & Database
- **Models** – Eloquent models and where they’re used
- **Model Relationships** – `hasMany`, `belongsTo`, etc. detection
- **Migrations** – Tables and fields defined in migration files
- **Database Schema** – Flattened schema from migration data
- **Seeders & Factories** – Test data-related classes and their usage

### 🧩 Frontend / Assets
- **JavaScript** – JS files and their API calls or route references

### ⚙️ App Structure & Configuration
- **Middleware** – All custom and Laravel middleware
- **Service Providers** – Registered service providers
- **Config Files** – Laravel config keys from `/config/*.php`
- **Config Usage** – Calls to `config('...')`
- **Environment Usage** – Calls to `env('...')`

### 🔐 Validation & Security
- **Validation Rules** – Inline and FormRequest rules
- **Authorization Map** – Gate, Policy, and Blade auth directive usage
- **Security Audit** – Potential `.env` leaks and config risks

### 🧪 Testing & QA
- **Tests** – Test classes, methods, and routes tested
- **Data Exporters** – PDF/Excel exports (`PDF::loadView`, `Excel::download`, etc.)
- **Manual QA** – Suggestions for manual quality checks

### 📚 Dependencies & Structure
- **Dependencies** – Composer dependencies (require & require-dev)
- **Service Dependencies** – Classes injected via Laravel’s container
- **Folder Structure** – Tree of your Laravel folder/file structure

### 🔗 Cross References
- **Events & Listeners** – Events, broadcasts, and listener classes
- **Component Relationships** – Connections between components (route → controller → model)
- **Master Reference** – Complete list of all components indexed by ID

---

## 🧠 Why Use Laravel Project Tracker?

- ✅ Visualize complex Laravel architectures instantly
- 🔍 Detect unused, missing, or mislinked components
- 🔗 Follow logical paths from View → Route → Controller → Model
- 📖 Auto-document your Laravel project for new team members
- 🧪 Assess testing and validation coverage
- 🛡️ Run a basic static security audit

---

## 💼 Who Should Use This?

| Role               | Benefit                                             |
|--------------------|-----------------------------------------------------|
| Laravel Developers | Understand codebase, refactor, or debug efficiently |
| QA Engineers       | Audit test coverage and URI-to-route matching       |
| Tech Leads         | Document systems and manage code reviews            |
| DevOps/Security    | Identify environment/config risks                   |
| Students & Learners| Explore Laravel project structure deeply            |

---

## 📊 Common Scenarios & How to Track Them

### ✅ 1. **Are all routes linked to controllers and views?**

- 📍Check `Web Routes`, `API Routes`, and `Route References`
- 🔗 Use cross-links to jump from route to controller to view
- 🛠️ Detect "orphaned routes" with no destination handler

---

### ✅ 2. **Which models are used and where?**

- 📍Open the `Models` sheet
- 🔗 Find where each model is used (controllers, views, etc.)
- 🔍 Check `Model Relationships` to verify DB associations

---

### ✅ 3. **Are there any environment/config risks?**

- ⚠️ Go to the `Environment Usage` and `Security Audit` sheets
- 🕵️‍♂️ Look for unguarded `env()` usage or sensitive config keys

---

### ✅ 4. **How well is the app tested?**

- 🧪 Browse the `Tests` and `Route References` sheets
- 🔍 Find routes not covered by any test class
- ✅ Use `Manual QA` for human-tested items checklist

---

### ✅ 5. **How can I onboard a new developer faster?**

- 📁 Start with `Dashboard` and `Folder Structure`
- 🔄 Use `Component Relationships` to show flow: route → controller → model → view
- 📚 Let them explore views via the `Blade Hierarchy`

---

## 🛠️ Installation

### ✅ Prerequisites

- Python 3.8+
- [`openpyxl`](https://pypi.org/project/openpyxl/)

### 💾 Install Dependencies

```bash
pip install openpyxl
```

---

## ▶️ How to Run

- From your terminal:
    `python laravel_project_tracker.py`

- By default, this will:
    Scan the parent directory of where the script is located
    Output an Excel file named laravel_project_tracker.xlsx
    Create a tracker_errors.log with any errors or missing references    

---

## 🔧 Optional Configuration

- To customize the scanning path or output file, create a config.json:
    {
      "project_root": "C:/Path/To/Laravel/Project",
      "output_file": "custom_filename.xlsx",
      "max_workers": 8
    }

- Then run the script again:
    `python laravel_project_tracker.py`

---

## 📁 Example Output   

- The Excel report contains:
    🔗 Hyperlinked IDs between related components (e.g., route ↔ controller ↔ view ↔ model)
    ✅ Usage and reference tracking
    ⚠️ Warnings for missing routes, insecure env usage, and unvalidated forms
    📂 Folder tree and class structures

- Use cases:
    🧭 Onboarding new developers
    📦 Client handovers
    🧪 Test coverage analysis
    🛡️ Static security reviews

---

## 📦 requirements.txt

- `openpyxl>=3.1.0`

---

## 📘 License

- This project is licensed under the MIT License.
- You're free to use, modify, share, or include it in commercial or private projects with proper attribution.

---

## 🙋 Contributions & Issues

- Found a bug? Want to request a feature?
- Open an issue or submit a pull request — contributions are welcome!

---

## 👨‍💻 Author

- Mohamed Shamil
- 🔗 GitHub – [@mohamed3shamil](https://github.com/mohamed3shamil)

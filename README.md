# Laravel Project Tracker 🧭

A comprehensive Python-based static analysis tool that scans Laravel projects and generates a fully cross-linked Excel report covering routes, controllers, models, views, tests, configs, and much more.

## 🚀 Features

- 📑 Excel report with 30+ sheets:
  - Routes (Web/API), Controllers, Models, Views
  - Blade Hierarchy, JavaScript URIs, Tests
  - Middleware, Config, Environment Variables
  - Livewire Components, Events, Seeders & Factories

- 🔁 Fully cross-linked data:
  - Route ↔ Controller ↔ View ↔ Model
  - Test URIs ↔ Routes
  - JS URIs ↔ Routes

- 🧠 Smart mapping + unique IDs
- 💡 Inline references and security audit
- ⚡ Multithreaded scanning

## 🛠️ Usage

```bash
pip install openpyxl
python laravel_project_tracker.py

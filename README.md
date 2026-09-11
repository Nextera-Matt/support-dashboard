<div align="center">

# 🎫 Support Operations Dashboard

**Real-time ticket aggregation across three platforms into one unified view — two-tier caching for near-instant load times.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)

</div>

---

> ⚠️ **This repo is a clean, from-scratch recreation for portfolio purposes.** It reimplements the real architecture I built at THG Ingenuity, using synthetic data generated locally — no real client data, credentials, or internal endpoints anywhere in this code.

## 🎯 The Problem

The support team was juggling **three separate ticketing systems** per shift (two Ubersmith instances + Zoho Desk), with no unified view of what was actually open.

## ✨ The Solution

```
   Ubersmith #1  ─┐
   Ubersmith #2  ─┼─▶  Aggregator  ─▶  L1 cache (memory, ~30s)
   Zoho Desk     ─┘                         │
                                             ▼
                                       L2 cache (file, ~5min)
                                             │
                                             ▼
                                       Dashboard UI
```

**Two-tier caching** is the core performance idea: an in-memory L1 cache absorbs rapid repeat requests, while a file-backed L2 cache absorbs the cost of the actual upstream API calls. This is what the "40x faster response times" figure on my site refers to.

## 🚀 Features

- 🔗 **Multi-source aggregation** — pulls from all three platforms through one interface
- ⚡ **Two-tier caching** — memory + file, dramatically cutting load times
- 🔐 **Role-based access control** — engineer / team-lead / admin, each seeing progressively more
- 🧪 **Fully runnable locally** — synthetic data seeds automatically, zero external dependencies

## 📋 Requirements

```
✓ PHP 8+
✓ pdo_sqlite extension
```

## 🎮 Usage

```bash
git clone https://github.com/Nextera-Matt/support-dashboard.git
cd support-dashboard
php -S localhost:8000 -t public
```

Visit `http://localhost:8000/?role=admin` (or `team_lead` / `engineer`) — mock tickets seed automatically on first run.

## 🛠️ Stack

<p align="center">
  <img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" />
</p>

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file.

## 📬 Support

<div align="center">

[![GitHub Issues](https://img.shields.io/github/issues/Nextera-Matt/support-dashboard)](https://github.com/Nextera-Matt/support-dashboard/issues)

[Open an Issue](https://github.com/Nextera-Matt/support-dashboard/issues) • [Visit Portfolio](https://matthodges.uk)

</div>

---

<div align="center">

**Made by [Matt Hodges](https://matthodges.uk)**

</div>

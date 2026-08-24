# 🕹️ Directions Control Panel

A simple web-based control panel with directional buttons (⬆️ ⬅️ ⏹️ ➡️ ⬇️) that sends the pressed direction to a PHP backend, which logs it into a MySQL database.

---

## 📂 Project Structure

```
📁 project/
├── 🌐 HTMLPage1.html   → Frontend UI with direction buttons
├── 🐘 direction.php     → Backend script that handles button POST requests
└── 🗄️ directions.sql    → Database schema (phpMyAdmin export)
```

---

## ⚙️ How It Works

1. 🖱️ User clicks one of the buttons: **Forward**, **Left**, **Stop**, **Right**, or **Backward**.
2. 📨 The form submits a POST request (`button` value) to `direction.php`.
3. 🔌 PHP connects to the MySQL database (`directions`).
4. 💾 The selected direction is logged into the database.
5. ✅ The chosen direction is displayed back on the page.

---

## 🗃️ Database

**Database name:** `directions`

| Column | Type    | Description        |
|--------|---------|---------------------|
| `s` 🛑  | int(20) | Stop                |
| `f` ⬆️  | int(20) | Forward             |
| `l` ⬅️  | int(20) | Left                |
| `r` ➡️  | int(20) | Right               |
| `b` ⬇️  | int(20) | Backward            |

📥 Import `directions.sql` into phpMyAdmin/MySQL to create the table.

---

## 🚀 Setup Instructions

1. 📦 Install **XAMPP** / **WAMP** / **MAMP** (Apache + MySQL + PHP).
2. 🗄️ Import `directions.sql` into your MySQL server via phpMyAdmin.
3. 📁 Place `HTMLPage1.html` and `direction.php` inside your server's `htdocs` (or `www`) folder.
4. ▶️ Start Apache & MySQL.
5. 🌍 Open `HTMLPage1.html` in your browser and start clicking! 🎮

---

## 🛠️ Requirements

- 🐘 PHP 7+ (with `mysqli` extension)
- 🐬 MySQL / MariaDB
- 🌐 Any modern web browser

---

## ⚠️ Known Issues / Notes

- 🐛 `direction.php` currently inserts into a `name` column, but the `directions` table doesn't have one — it uses `s`, `f`, `l`, `r`, `b` instead. This needs to be fixed for the insert to work correctly.
- 🔓 Database credentials (`root` with no password) are hardcoded — not safe for production. 🔒 Use environment variables or a config file instead.
- 🧹 SQL query is not using prepared statements — vulnerable to SQL injection. Consider using `mysqli::prepare()`.

---

## 💡 Possible Improvements

- ✨ Add prepared statements for security
- 🎨 Improve UI styling & responsiveness
- 📊 Add a history log/table of past commands
- 🔄 Add real-time feedback via AJAX (no page reload)

---

## 📝 License

Free to use and modify. 🎉

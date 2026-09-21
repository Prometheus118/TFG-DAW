# 🎬 Estelar ▶ Film

> Web application to discover movies and series and find out where to stream, rent or buy them — built as the final degree project (Proyecto de Desarrollo de Aplicaciones Web) for the Higher Technician in Web and Multiplatform Application Development at IES La Arboleda, 2021/2022.

**Author:** Christian Atienza Masa
**Tutor:** Miguel Ángel Hernández Capitán

---

## 📖 About the project

Estelar Film lets users browse information about every movie and series — synopsis, trailer, cast, ratings, genre, duration, director — and see where each title is available to **stream, rent or buy**. It was inspired by JustWatch and FilmAffinity, aiming to combine JustWatch's "find where to watch" approach with a clean, easy-to-use interface.

Users register and log in to access the home page, choose between Movies or Series (the Series section is a "coming soon" placeholder), browse the latest news, read about the team behind the app, get in touch through a contact form, and view a **Power BI dashboard of the top movies of 2017**. Selecting a movie opens a detail page with its full information and a link straight to the streaming platform where it's available.

A separate **admin area** lets authorized staff update and delete movie and series records.

## ✨ Features

- 🔐 User registration, login and password change
- 🎞️ Movie catalog with detail pages (rating, genre, runtime, director, synopsis, cast, poster)
- 📺 "Where to watch" links to streaming, rental and purchase platforms
- 📰 Latest movie news section
- 👥 Team / about page with a direct email link
- ✉️ Contact form (stored in the database via a stored procedure)
- 📊 Embedded Power BI report — Top Movies of 2017
- 🛠️ Admin panel to update and delete movies/series (role-restricted)
- 📱 Responsive layout (Bootstrap) targeting desktop, tablet and mobile

## 🧱 Tech Stack

| Layer | Technology |
|---|---|
| Architecture | MVC (Model-View-Controller) |
| Front-End | HTML5, CSS3, JavaScript, Bootstrap 4.0 |
| Back-End | PHP |
| Database | MySQL (via XAMPP / phpMyAdmin), stored procedures |
| Analytics | Microsoft Power BI |
| Tooling | Visual Studio Code, XAMPP (Apache + MySQL + PHP) |

## 🗄️ Data model

The database is organized around four main entities:

- **Users** — username and password
- **Contact messages** — ID, username, email, subject and issue, saved through the `InsertarEmail` stored procedure
- **Movies** — code, unique name, director, cast, description, release date, genre
- **Series** — code, unique name, creator, cast, description, first air date, genre, number of seasons

A dedicated dataset also tracks the **Top 2017 Movies** (Movie Index, Awards, Box Office, Cast & Crew, DVD, Genre, IMDb ID, Plot, Poster, Rated, Runtime, Title, Type, Website, Year) that feeds the Power BI report.

Login/authorization is resolved through the `mostrarUsuarioporNombre` stored procedure, which the system uses to validate credentials before granting access.

## 🚀 Getting started

The app runs on a classic PHP + MySQL stack via XAMPP.

1. **Install XAMPP** (Apache, MySQL/MariaDB, PHP and phpMyAdmin) from [apachefriends.org](https://www.apachefriends.org/index.html).
2. During setup, make sure **Apache**, **MySQL** and **PHP** are selected, along with **phpMyAdmin**.
3. Start the **Apache** and **MySQL** modules from the XAMPP control panel.
4. Import the project's database (tables, relationships, stored procedures) through phpMyAdmin.
5. Copy the project files into XAMPP's `htdocs` folder.
6. Open the app in your browser at `http://localhost/estelar-film` (adjust the path to match your folder name) and go to `loginDefinitivo.php` to log in.
7. (Optional) Install [Visual Studio Code](https://code.visualstudio.com/) if you plan to edit the project.

## 🔭 Possible future work

- Show login errors inline instead of redirecting on a failed attempt
- Finish and launch the Series section
- Replace hard-coded page data with stored-procedure calls backed by the database
- Strengthen session validation across the whole app
- Expand the database with more tables, data and procedures
- Add a search bar as the catalog grows
- Run an SEO/web-positioning study to grow the user base

## 📄 About this document

This README summarizes the original project report ("Estelar Film" — Proyecto de Desarrollo de Aplicaciones Web, IES La Arboleda, curso 2021/2022), which also covers project planning, a market/competitor analysis (JustWatch, FilmAffinity), functional and non-functional requirements, use-case specifications, UI/UX design, and a full illustrated installation manual.

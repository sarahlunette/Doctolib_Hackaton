# 🩺 Doctolib Hackathon Project

## 📌 Overview

This repository contains a **hackathon project developed for the Doctolib AI Action Summit / Hackathon** where the goal was to prototype a healthcare‑related web application with user authentication, backend services, and database integration. The project leverages:

✔ Python & **Streamlit** for the interactive web UI
✔ **MongoDB** as a backend data store orchestrated with Docker Compose
✔ A simple authentication flow
✔ A scalable structure suitable for further extension

> *Note:* The current README is placeholder — this document replaces it with full instructions, architecture, and usage guidelines. ([GitHub][1])

---

## 📁 Repository Contents

```
├── .gitattributes
├── .gitignore
├── docker-compose.yml
├── docker-compose‑working‑mongo.yaml
├── ilovethesea.png
├── mong_init.js.rtf
├── Notes.rtf
├── README.md
├── streamlit/              # Frontend Streamlit application
├── requirements.txt
```

* **Streamlit Folder** – Contains the Python frontend code (e.g., `Login.py`). ([GitHub][1])
* **Docker Compose files** – Configurations to bring up MongoDB for local development with or without initialization scripts. ([GitHub][1])
* **Mongo init script** – Seed/setup script for MongoDB (provided as RTF). ([GitHub][1])
* **Requirements file** – Lists all Python dependencies. ([GitHub][1])
* **Misc docs** – Notes/RFT with internal details or auxiliary configs. ([GitHub][1])

---

## 🚀 Features

### 🔐 Authentication & Login

* A Streamlit‑based login page as the app entry point (`Login.py`). ([GitHub][1])
* Future enhancements could include robust auth flows using packages like **streamlit_authenticator** or **streamlit_login_auth_ui** (not included by default). ([GitHub][2])

---

### 🗄 Backend Database

The project uses **MongoDB** as the data store:

* Docker Compose provisions a local MongoDB instance.
* A **mongo‑init.js** script seeds initial collections or users (if included via `docker‑compose‑working‑mongo.yaml`). ([GitHub][1])

---

## 🛠️ Prerequisites

Make sure you have installed the following:

* **Python 3.9+**
* **Docker** & **Docker Compose**
* **pip** for Python dependency installation
* Optional: A terminal/IDE such as VS Code or PyCharm

---

## 📦 Installation

1. **Clone the Repository**

```bash
git clone https://github.com/sarahlunette/Doctolib_Hackaton.git
cd Doctolib_Hackaton
```

---

2. **Install Dependencies**

```bash
pip install ‑r requirements.txt
```

Typical packages include:

* `streamlit` – for the web UI
* `pymongo` – MongoDB driver
* Other utilities as defined in `requirements.txt` ([GitHub][1])

---

## 🐳 Start the Development Environment

Before running the Streamlit app, bring up the backend services:

### 🔹 Option A — Standard MongoDB

```bash
docker compose up ‑d
```

This uses the main `docker‑compose.yml`. ([GitHub][1])

---

### 🔹 Option B — MongoDB with Initialization

To seed MongoDB with data:

```bash
docker compose ‑f docker‑compose‑working‑mongo.yaml up ‑d
```

This includes the mongo init script defined in the project. ([GitHub][1])

---

## 📊 Running the Application

Once the services are up:

```bash
streamlit run streamlit/Login.py
```

This launches the login interface in your browser on `localhost:8501` by default. ([GitHub][1])

---

## 🧠 Architecture Overview

```
┌────────────────────┐
│      Frontend      │
│  Streamlit App UI  │ ── interacts via API or directly with backend
└────────────────────┘
           ↓
┌────────────────────┐
│     Python Logic   │
│  (Data fetching &  │
│   business rules)  │
└────────────────────┘
           ↓
┌────────────────────┐
│     MongoDB DB     │
│   Docker‑composed  │
│   database service │
└────────────────────┘
```

---

## 💡 Next Improvements

Here are suggestions for taking the project further:

### Authentication

Use a proper auth library such as:

* **streamlit_authenticator** 🎯 for secure usernames/passwords and hashed credentials. ([GitHub][3])
* **streamlit_login_auth_ui** — simpler drag‑and‑drop login UI. ([GitHub][2])

---

### Deployment

* Host the Streamlit app (e.g., via **Streamlit Community Cloud** or **Heroku**).
* Use environment variables for MongoDB credentials and production settings.
* Add HTTPS / secure login sessions.

---

## 📄 Contribution

Contributions are welcome! Typical ways to contribute:

* Clear up authentication flow
* Add user registration features
* Enhance UX/UI with Streamlit components
* Add CI/CD automation

---

## 🏷️ License

This project currently has no declared license — you may want to add one (e.g., **MIT License**) for open use.

---

## 📌 Acknowledgements

Built as part of the **Doctolib Hackathon / AI Action Summit**, where participants prototype AI and app ideas in healthcare settings. ([About Doctolib][4])


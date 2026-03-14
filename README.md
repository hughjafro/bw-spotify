# 🎵 SpotiFinder

> A Spotify-inspired dashboard app for browsing and visualizing audio features across 116,000+ songs.

---

## 📖 Overview

SpotiFinder is a full-stack web application that lets users explore and visualize audio features from Spotify's Kaggle dataset of over 116,000 songs. Users can search for tracks, inspect audio characteristics like danceability, energy, and acousticness, save favorites, and receive song recommendations powered by a custom data science model.

The project was a collaborative build week effort between Full Stack Web (FSW), UX, and Data Science students at Lambda School.

- 🌐 **Live App:** [https://bw-spotify.netlify.com](https://bw-spotify.netlify.com)
- 🔌 **API:** [https://bw-spotify-backend.herokuapp.com/api](https://bw-spotify-backend.herokuapp.com/api)

---

## ✨ Features

- 🔍 **Search** — Query songs by title or artist across 116k+ tracks
- 📊 **Audio Feature Visualization** — Explore metrics like danceability, energy, valence, tempo, and more
- 🎯 **Song Recommendations** — ML-powered similar song suggestions for any selected track
- ❤️ **Favorites** — Save and manage a personal list of favorite songs
- 🔐 **Authentication** — JWT-based user registration and login

---

## 🏗️ Architecture

The project is split across four repositories:

| Repo | Tech | Description |
|------|------|-------------|
| [`frontend`](https://github.com/bw-spotify/frontend) | React, JavaScript, CSS | User interface and data visualizations |
| [`backend`](https://github.com/bw-spotify/backend) | Node.js, Express, Knex, PostgreSQL | REST API, auth, and data layer |
| [`data-science`](https://github.com/bw-spotify/data-science) | Python, Jupyter Notebook | Song recommendation model |
| [`user-interface`](https://github.com/bw-spotify/user-interface) | CSS | UX design and component styling |

---

## 🔌 API Reference

**Base URL:** `https://bw-spotify-backend.herokuapp.com/api`

### Auth

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/register` | Register a new user |
| POST | `/api/login` | Login and receive a JWT |

### Songs

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/songs` | Get paginated/sorted list of songs |
| GET | `/api/songs?id=<id>` | Get a song by ID + 10 recommended similar songs |
| GET | `/api/songs/search?q=<query>` | Search songs by name |

**Example — Get Song with Recommendations:**
```
GET /api/songs?id=5RkS8NsjKoSCh5jpctvEdT
```

```json
{
  "artist_name": "ｊａｒｊａｒｊｒ",
  "track_name": "Manhattan Warmonger",
  "danceability": 0.783,
  "energy": 0.621,
  "valence": 0.798,
  "tempo": 84.552,
  "similars": [
    { "artist_name": "Atmosphere", "track_name": "Ha, This One Is About Alcohol Too" }
  ]
}
```

### Favorites

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/faves` | Get all favorites for logged-in user |
| POST | `/api/faves` | Add a song to favorites |
| DELETE | `/api/faves` | Remove a song from favorites |

---

## 🚀 Local Setup

### Prerequisites

- Node.js & Yarn
- PostgreSQL

### Backend

```bash
git clone https://github.com/bw-spotify/backend.git
cd backend
yarn install
# Add a .env file with your DATABASE_URL and JWT_SECRET
yarn dev
```

### Frontend

```bash
git clone https://github.com/bw-spotify/frontend.git
cd frontend/spotify
yarn install
yarn start
```

### Data Science

```bash
git clone https://github.com/bw-spotify/data-science.git
cd data-science
pip install -r requirements.txt
jupyter notebook
```

---

## 🧰 Tech Stack

**Frontend**
- React
- JavaScript (ES6+)
- CSS3

**Backend**
- Node.js / Express
- Knex.js (query builder)
- PostgreSQL / SQLite3
- JWT Authentication (`jsonwebtoken`, `bcryptjs`)
- Helmet, CORS, Morgan

**Data Science**
- Python
- Jupyter Notebook
- Spotify Kaggle Dataset (116k+ songs)

---

## 👥 Team

Built during Lambda School Build Week by a cross-functional team of FSW, UX, and Data Science students.

| Role | Contributor |
|------|-------------|
| Backend | See [contributors](https://github.com/bw-spotify/backend/graphs/contributors) |
| Frontend | See [contributors](https://github.com/bw-spotify/frontend/graphs/contributors) |
| Data Science | See [contributors](https://github.com/bw-spotify/data-science/graphs/contributors) |
| UX Design | See [contributors](https://github.com/bw-spotify/user-interface/graphs/contributors) |

---

## 📄 License

[MIT](https://github.com/bw-spotify/backend/blob/master/LICENSE)

---

> *This project is not affiliated with or endorsed by Spotify AB. Built for educational purposes using publicly available Kaggle data.*

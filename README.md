# ToDoApp – Docker Projekt  
Nginx + Express + PostgreSQL (Docker Compose)

---

## 📦 Projektbeschreibung

Diese Anwendung ist eine mehrcontainerfähige ToDo-Webanwendung.

Sie besteht aus:

- **Nginx** → Webserver (Frontend)
- **Express (Node.js)** → Backend API
- **PostgreSQL** → Datenbank
- **Docker Compose** → Orchestrierung
- **Docker Volume** → Persistente Speicherung

Benutzer können ToDos erfassen, welche in der PostgreSQL-Datenbank gespeichert werden.

---

# 🚀 Start für Lehrperson (Play with Docker)

Die Anwendung kann mit folgenden Befehlen gestartet werden:

```bash
git clone https://github.com/Marco-Ermel/-bungsprojekte_ToDoApp.git
cd -bungsprojekte_ToDoApp
docker compose -f pfad/docker-compose/docker-compose.yml up -d --build
```

---

## 🌐 Zugriff

Nach dem Start:

- Port **8080** öffnen
- Lokal:  
  `http://localhost:8080`

In Play with Docker:
→ Port 8080 anklicken

---

## 🧪 Persistenz-Test

Container stoppen:

```bash
docker compose -f pfad/docker-compose/docker-compose.yml down
```

Neu starten:

```bash
docker compose -f pfad/docker-compose/docker-compose.yml up -d
```

Gespeicherte ToDos bleiben erhalten.  
Die Daten werden im Docker Volume `dbdata` gespeichert.

---

## 🏗 Architektur

| Service | Funktion |
|----------|----------|
| web | Nginx Webserver |
| app | Express Backend (REST API) |
| db | PostgreSQL Datenbank |
| dbdata | Persistentes Volume |

---

## 🐳 Docker Image

Ein eigenes Docker Image wurde erstellt und in eine Container Registry gepusht.

Beispiel:

```
ghcr.io/marco-ermel/todoapp:1.2
```

Nachweis erfolgt per Screenshot des erfolgreichen `docker push`.

---

## 🛠 Container prüfen

Laufende Container anzeigen:

```bash
docker ps
```

Logs anzeigen:

```bash
docker logs uebungsprojekt_web
docker logs uebungsprojekt_app
docker logs uebungsprojekt_db
```

---

## 🔧 Stoppen der Anwendung

```bash
docker compose -f pfad/docker-compose/docker-compose.yml down
```

---

## 👤 Autor

Marco Ermel  
GitHub: Marco-Ermel  
E-Mail: mer152473@stud.gibb.ch

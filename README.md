# Docker Projekt – ToDoApp  
**Nginx + Express + PostgreSQL (Docker Compose)**

---

## Projektbeschreibung

In diesem Projekt wurde eine mehrcontainerfähige Docker-Anwendung erstellt.

Die Anwendung besteht aus:

- Nginx Webserver (Frontend)
- Express Backend (Node.js API)
- PostgreSQL Datenbank
- Docker Compose zur Orchestrierung
- Persistente Speicherung über Docker Volume

Benutzer können Einträge erfassen, welche in der Datenbank gespeichert und angezeigt werden.

---

## Architektur

| Service | Beschreibung |
|----------|-------------|
| web | Nginx Webserver (Port 8080) |
| app | Express Backend (REST API) |
| db | PostgreSQL Datenbank |
| volume dbdata | Persistente Datenspeicherung |

---

## Start der Anwendung (Play with Docker oder Linux)

```bash
git clone https://github.com/Marco-Ermel/-bungsprojekte_ToDoApp.git
cd -bungsprojekte_ToDoApp
docker compose -f pfad/docker-compose/docker-compose.yml up -d --build
```

---

## Zugriff

Webseite öffnen:

```
http://localhost:8080
```

In Play with Docker:
Port 8080 öffnen.

---

## Persistenz-Test

Nach folgendem Befehl:

```bash
docker compose -f pfad/docker-compose/docker-compose.yml down
docker compose -f pfad/docker-compose/docker-compose.yml up -d
```

bleiben gespeicherte Daten erhalten.

Die Daten werden im Docker Volume `dbdata` gespeichert.

---

## Docker Image (Push in Registry)

Das Image wurde in eine Container Registry gepusht.

Beispiel:

```
ghcr.io/marco-ermel/todoapp-web:1.0
ghcr.io/marco-ermel/todoapp-app:1.0
```

Nachweis erfolgt per Screenshot des erfolgreichen `docker push`.

---

## Änderungen veröffentlichen

### Frontend ändern

```bash
git add .
git commit -m "Update Frontend"
git push
```

### Backend ändern

```bash
docker compose -f pfad/docker-compose/docker-compose.yml up -d --build
git add .
git commit -m "Update Backend"
git push
```

---

## Container anzeigen

```bash
docker ps
```

## Logs anzeigen

```bash
docker logs uebungsprojekt_web
docker logs uebungsprojekt_app
docker logs uebungsprojekt_db
```

---

## Verwendete Technologien

- Docker
- Docker Compose
- Nginx
- Node.js / Express
- PostgreSQL
- GitHub

---

## Autor

Marco Ermel  
mer152473@stud.gibb.ch# -bungsprojekte_ToDoApp

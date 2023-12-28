# Todo List

## Simple Todo List SPA built with Django REST Framework and Vue.js

### Features
- Create, read, and delete todo items
- Authentication and authorization with Auth Token
- Dockerized with Docker Compose
- Deployed to AWS EC2

### Technologies Used
- Django
- Django REST Framework
- Vue.js
- Axios
- Docker
- Docker Compose
- PostgreSQL
- AWS EC2


### Local Setup
1. Clone the repository
```bash
# for HTTPS
$ git clone https://github.com/FlashDrag/django-vue-todo.git
# OR if you have SSH keys set up for GitHub use:
$ git clone git@github.com:FlashDrag/django-vue-todo.git
```
2. Add a `.env` file to the root directory. See `.env.example`
```bash
$ cp .env.example .env
```
3. Buid docker images and run containers using development docker-compose file. It will start the Django server on port 8000 and the Vue.js dev server on port 8080. The Vue.js dev server is not built for production.
```bash
$ docker compose -f docker-compose.dev.yml up --build
```
4. Navigate to `localhost:8080` for the Vue.js app or `localhost:8000/admin` for the Django REST Framework browsable API.

#### Docker Compose Volumes for Development
- Backend: `./backend:/app`
- Frontend: `./frontend:/app`
- Django Static Files:
    - Backend: `django-static:/app/static`
    - Nginx: `django-static:/usr/src/app/static`
- PostgreSQL Data: `dbdata:/var/lib/postgresql/data/`

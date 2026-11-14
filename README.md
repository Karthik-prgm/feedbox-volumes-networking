# FeedBox volumes and networking

FeedBox is a feedback collector using PostgreSQL, an Express API, and an Nginx frontend.

## Run

1. Copy `.env.example` to `.env`.
2. Replace the local placeholder password in `.env` with a value of your choice. Keep `.env` private.
3. Start the stack with `docker compose up --build`.

- Frontend: http://localhost:3000
- API: http://localhost:5000/api/messages

For development hot reload, use `docker compose -f docker-compose.yml -f docker-compose.dev.yml up --build`.

PostgreSQL data is stored in the named `postgres_data` volume. The database is reachable only from the API over the private database network; it has no published host port.

Do not commit `.env` or `node_modules`.

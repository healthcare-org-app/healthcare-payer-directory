# payer-directory

payer-directory — domain: insurance

- **Port:** 8803
- **Language:** Python 3.11 + Flask
- **Database:** `insurance` (Postgres, table `payer_directory`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/payer_directory/`          |
| POST      | `/api/payer_directory/`          |
| GET       | `/api/payer_directory/<id>`      |
| PUT/PATCH | `/api/payer_directory/<id>`      |
| DELETE    | `/api/payer_directory/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```

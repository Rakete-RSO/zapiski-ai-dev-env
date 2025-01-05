# zapiski-ai-dev-env

## HTTP requests

Are provided in Postman collection file in this repository.

## Meilisearch

### Setup

1. Run `docker-compose up -d` to start the meilisearch.
2. Create a new index

```bash
curl -X POST 'http://127.0.0.1:7700/indexes' \
-H 'Authorization: Bearer ${MEILI_MASTER_KEY}' \
-H 'Content-Type: application/json' \
-d '{
  "uid": "chats",
  "primaryKey": "id"
}'
```

3. Make `user_id` a filterable attribute. Locally, I ran this in python with

```python
meilisearch_index_chats.update_filterable_attributes(["user_id", "name", "id"])
```

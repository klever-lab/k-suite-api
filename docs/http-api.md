# HTTP API

## Handler construction

`httpapi.NewHandler` returns a standard `http.Handler` backed by `http.NewServeMux`.

## Routes

### `GET /health`

Returns HTTP 200 with the JSON body:

```json
{"status":"ok"}
```

### `GET /ready`

Returns HTTP 200 with the JSON body:

```json
{"status":"ready"}
```

Readiness currently does not check dependencies. Database and other dependency checks are planned for later.

## Responses and unmatched routes

JSON responses set `Content-Type` to `application/json`, write the status first, and encode the value with `json.Encoder`, which adds a trailing newline. An unmatched route is handled by the standard mux and returns HTTP 404.

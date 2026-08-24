# K Suite API

The API-first core for the K Suite tools.

## Run locally

```bash
go run ./cmd/api
```

The server listens on `http://127.0.0.1:8080` by default. Set `API_ADDR` to change the bind address.

## Test

```bash
go test ./...
```

## Initial scope

The first server slice only establishes the HTTP process, health endpoints, structured logging, timeouts, and graceful shutdown. Storage connections, authentication, share links, and jobs will be added behind this boundary.

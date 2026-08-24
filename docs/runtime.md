# Runtime

## Entry point

The executable starts in `cmd/api/main.go`. It creates a JSON logger writing to standard output, constructs an `http.Server`, and serves the handler from `internal/httpapi`.

## Configuration

`API_ADDR` controls the server bind address. If it is unset or empty, the address is `:8080`. The README's default URL is `http://127.0.0.1:8080`.

## Server settings

The HTTP server uses these timeouts:

- `ReadHeaderTimeout`: 5 seconds
- `IdleTimeout`: 60 seconds
- `WriteTimeout`: 30 seconds

## Logging and lifecycle

Startup is logged at info level as a JSON event with the configured address. The process listens for `os.Interrupt` and `SIGTERM` through a context. On either signal it performs graceful shutdown with a 10-second timeout.

If `ListenAndServe` returns an error other than `http.ErrServerClosed`, the process logs the error and exits with status 1. A shutdown failure is handled the same way.

## Current scope

The initial server slice includes the HTTP process, health endpoints, structured logging, timeouts, and graceful shutdown. Storage connections, authentication, share links, and jobs are not implemented.

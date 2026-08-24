# Testing

The package-level tests are in `internal/httpapi/handler_test.go` and use `httptest` against a freshly constructed handler.

Coverage currently includes:

- `TestHealth`, which verifies `GET /health` returns HTTP 200 and the exact JSON response body.
- `TestUnknownRoute`, which verifies an unmatched path returns HTTP 404.

Run the full test suite with:

```bash
go test ./...
```

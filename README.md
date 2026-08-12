# basic_http_server_go

A minimal Go HTTP server with a tiny in-memory user manager.

What it does:
- Starts on port 8080.
- Serves:
	- `/` : welcome message
	- `/goodbye/` : goodbye message
	- `/hello/?user=NAME` : hello by query parameter
	- `/responses/{user}/hello/` : hello by path parameter (tests set path value)
	- `POST /json` : accepts JSON { "FirstName": "..." } and replies with a hello
	- `POST /add-user` : add a user (JSON with FirstName, LastName, Email) — returns 201
	- `POST /get-user` : retrieve a user (JSON with FirstName, LastName) — returns user JSON
	- `POST /user/hello` : greet a user using `userFirst` and `userLast` headers

How to run:
```bash
cd basic_http_server_go
go run .
```

Run tests:
```bash
cd basic_http_server_go
go test ./...
```

Notes:
- Uses `internal/users` for a simple in-memory user manager.
- Data is not persistent; it's for examples and tests only.

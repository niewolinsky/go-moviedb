# MovieDB - Go REST API serving submitted movies data
Framework-less REST API, allowing you to store and retrieve simple movie data in JSON format. Follows standard good practices regarding UX and HTTP.

Application created as a part of my learning journey using Go as web back-end, it is not production ready.

## Features:
- Version control enabled database schema based on migrations
- Token-based user authentication and permission-based authorization
- Simple metrics exposed as an endpoint + comprehensive command line logger during runtime
- New user registration email with activation process
- Simple built-in rate limiting configurable from command line arguments
- Sending and retrieving movie data
- Filtering, sorting and pagination based on PostgreSQL methods, when pulling the data

## Running:
After configuring PostgreSQL database on your server, create `.env` file in project's root directory with KEY=VALUE:
MOVIE_DB_DSN={YOUR_POSTGRE_DSN}.

Then run database migrations using *migrate* tool and *task* build tool. Both dependencies have to be installed.

```bash
$ [task|go-task] db/migrations/up
```

Use script to easily run app

```bash
$ [task|go-task] audit
$ [task|go-task] run/api #or build/api
```
Lastly don't forget to change SMTP credidentals to your provider in `main.go`, as the application requires sending registration email.

## Todo:
- Password reset feature

## Stack:
- Go 1.19 + [fasthttp](https://github.com/valyala/fasthttp)
- PostgreSQL 14.5
- [Migrate](https://github.com/golang-migrate/migrate)
- [Task](https://github.com/go-task/task)

## Credits:
Application was heavily inspired by [Alex Edward's - Let's Go Further](https://lets-go-further.alexedwards.net/) book.
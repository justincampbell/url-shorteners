# URL Shorteners

* [What?](#what)
* [Requirements](#requirements)
* [The URL Shortener](#the-url-shortener)
* [API](#api)
* [Implementations](#implementations)

## What?

I want to learn more languages. Mostly, I'm interested in:

* Learning the basics and best practices of the language
* How to structure a project, and development workflow
* Testing, and tools that help a TDD cycle
* Deployability to Heroku

## Requirements

This is what I think the example project needs:

* Uses HTTP
* Has some sort of write workload
* Requires storage/state that can remain in-memory
* Straightforward to test
* Benchmarkable, if I choose to do that at some point

## The URL Shortener

I need something interesting to build, but not too complex that it would take
a long amount of time or result in immense frustration. I think a URL shortener
is a good compromise of the requirements above.

## API

### `GET /`

`302 Redirect` to this page

### `GET /shorten?url=[url]`

Create a new short URL, and respond with `201 Created` along with the path to
the token as the body (ex: `/abc123`).

Each shorten request will create a new token, regardless if it already exists
as another token (mostly for simplicity and performance).

Ideally, we would URL-decode and validate the URL, but I'm not concerned with
this to start. For now, it should respond with `400 Bad Request` if the url is
blank.

### `GET /:token`

`302 Redirect` to the full URL, or `404 Not Found` if the token was not found.

## Implementations

* [Clojure](https://github.com/justincampbell/url-shortener-clojure)
* [CoffeeScript](https://github.com/justincampbell/url-shortener-coffeescript)
* [Elixir](https://github.com/justincampbell/url-shortener-elixir)
* [Go](https://github.com/justincampbell/url-shortener-go)
* [Haskell](https://github.com/justincampbell/url-shortener-haskell)
* [JavaScript](https://github.com/justincampbell/url-shortener-javascript)
* [Python](https://github.com/justincampbell/url-shortener-python)
* [Ruby](https://github.com/justincampbell/url-shortener-ruby)

### In-progress

* [C](https://github.com/justincampbell/url-shortener-c)
* [Erlang](https://github.com/justincampbell/url-shortener-erlang)
* [Rust](https://github.com/justincampbell/url-shortener-rust)
* [Scala](https://github.com/justincampbell/url-shortener-scala)

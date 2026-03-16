# Tally Counter REST API (Task 2)

This project implements a simple REST API using Express that provides a tally counter.  
The application also uses Winston for logging.

## Requirements

- Node.js 18
- Express 4.18.2
- Winston 3.11.0

## Installation

Clone the repository:

`git clone https://github.com/ekh0o/Tally-Counter-API.git`

Navigate to the project directory:

`cd tally-counter-api`

Install dependencies:

`npm install`

## Running the Server

Start the server with:

`node src/main.js`

The server runs on:

`http://localhost:3000`

## API Endpoints

### Read Counter

`GET /counter-read`

Returns the current counter value.

Example response:

`{
  "counter": 0
}`

---

### Increase Counter

`GET /counter-increase`

Increases the counter by one and returns the new value.

Example response:

`{
  "counter": 1
}`

---

### Reset Counter

`GET /counter-reset`

Resets the counter to zero.

Example response:

`{
  "counter": 0
}`

## Counter Behaviour

The counter:

- Stores an integer value in memory
- Can be read
- Can be increased
- Can be reset to zero

Counter logic is implemented in:

`src/counter.js`

## Logging

Logging is implemented using Winston.

Log configuration is defined in:

`src/logger.js`

Logs are written to:

logs/error.log  
logs/combined.log

### Log Syntax

Main events:

[MAIN] Starting  
[MAIN] Stopping  

Endpoint logs:

[ENDPOINT] `GET '/counter-read'`

Counter logs:

[COUNTER] read 0  
[COUNTER] increase 1  
[COUNTER] zeroed 0  

## Testing the API

A REST client test file is included:

`rest.http`

Example request:

`GET http://localhost:3000/counter-read`

This file can be used with the VS Code REST Client extension.

## Project Structure

.
├── package-lock.json
├── package.json
├── README.md
├── rest.http
└── src
    ├── logger.js
    ├── main.js
    ├── counter.js
    └── routes.js

## .gitignore

The repository excludes reproducible and environment-specific files:

node_modules/ \
logs/ \
.env \
.DS_Store

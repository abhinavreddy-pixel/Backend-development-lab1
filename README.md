# Lab 1: Node.js and Express Server

## Student Details

- **Name:** ABHINAV REDDY
- **Registration Number:** 252U1R9173
- **Section:** CSE GEN-AI 2C
- **Course:** Backend Development Fundamentals
- **Lab Number:** 01

## Live Link
https://backend-development-lab1-eight.vercel.app/

If you have not deployed the project yet, write:

> Not deployed yet. The server runs locally at `http://localhost:3000`.

## Objective

The objective of this lab is to create a basic web server in two ways:

1. Using Node.js’s built-in `http` module.
2. Using Express.js to create routes and return the correct HTTP status codes.

## Technologies Used

- Node.js
- Express.js
- JavaScript
- npm
- Visual Studio Code

## Project Structure

```text
Backend lab1/
├── screenshots/
│   ├── home.png
│   ├── about.png
│   ├── time.png
│   └── not-found.png
├── node_modules/       # Installed locally; do not submit to GitHub
├── package.json
├── package-lock.json
├── .gitignore
├── server-http.js
├── server.js
└── README.md
```

## Requirements

- Node.js and npm installed
- Visual Studio Code or another code editor
- A terminal opened in this project folder

Check that Node.js is installed:

```powershell
node --version
```

In PowerShell, if the `npm` command is blocked by the script execution policy, use `npm.cmd`:

```powershell
& "C:\Program Files\nodejs\npm.cmd" --version
```

## Installation

Open the VS Code terminal in this folder and install the project dependencies:

```powershell
& "C:\Program Files\nodejs\npm.cmd" install
```

Express is listed as a project dependency in `package.json`. The install command reads that file and installs the required packages into `node_modules`.

If you are setting up the project for the first time and do not yet have a `package.json`, run:

```powershell
& "C:\Program Files\nodejs\npm.cmd" init -y
& "C:\Program Files\nodejs\npm.cmd" install express
```

## How to Run the Basic HTTP Server

The `server-http.js` file uses Node.js’s built-in `http` module and returns the text `Hello`.

Run:

```powershell
node server-http.js
```

Open this address in a browser:

```text
http://localhost:3000
```

Stop the server by clicking in the terminal and pressing **Ctrl+C**.

## How to Run the Express Server

Make sure the basic HTTP server is stopped first. Only one server can use port `3000` at a time.

Run:

```powershell
node server.js
```

When the server starts, the terminal should show:

```text
Express server running at http://localhost:3000
```

Open the endpoints below in your browser. Stop the server with **Ctrl+C** when you are finished.

## Endpoints

| Method | Path | Description | Expected Status |
|---|---|---|---:|
| GET | `/` | Displays a welcome message | 200 OK |
| GET | `/about` | Returns my name and section as JSON | 200 OK |
| GET | `/time` | Returns the current date and time as JSON | 200 OK |
| GET | Any undefined path, such as `/anything` | Returns a not found message | 404 Not Found |

## Screenshots

Place your screenshots in the `screenshots` folder. The image names below should match the names of your actual screenshot files.

### Home route

URL: `http://localhost:3000/`

![Home route response](screenshots/home.png)

### About route

URL: `http://localhost:3000/about`

![About route response](screenshots/about.png)

### Time route

URL: `http://localhost:3000/time`

![Time route response](screenshots/time.png)

### Unknown route

URL: `http://localhost:3000/anything`

![404 not found response](screenshots/not-found.png)

## How I Checked the Status Codes

I opened each route in the browser and checked its response in the browser’s developer tools:

1. Open the route in the browser.
2. Press **F12** to open Developer Tools.
3. Select the **Network** tab.
4. Refresh the page.
5. Select the request and check its **Status Code**.

The expected status is `200` for the three defined routes and `404` for an undefined route.

## Understanding `package.json`

`package.json` stores information and dependency settings for this Node.js project.

- **name:** Project name.
- **version:** Project version.
- **description:** Short description of the project.
- **main:** The default entry file listed for the package.
- **scripts:** Short commands that can be run with npm.
- **keywords:** Search terms that describe the project.
- **author:** Project author.
- **license:** License setting for the project.
- **type:** JavaScript module format. `commonjs` allows `require(...)`.
- **dependencies:** Packages the application needs to run, such as Express.

`node_modules` contains the actual installed packages. It can be recreated by running `npm install`, so it should not be committed to GitHub.

## Problems Faced and Solutions

PowerShell blocked the `npm` command because it tried to run `npm.ps1` while script execution was disabled. I used the Windows command file directly:

```powershell
& "C:\Program Files\nodejs\npm.cmd" install
```

[Add any other problems you encountered and how you solved them.]

## Git and Submission Notes

- Keep this `lab-01` folder in the course repository.
- Include this README and the screenshots folder in the submission.
- Do not commit `node_modules`.
- Do not commit or share `.env` files.
- Commit changes regularly with clear messages.
- Submit the GitHub repository link to the instructor.
- Make the repository public or share access with the instructor.

## Viva Questions

### What is the difference between `package.json` and `node_modules`?

`package.json` records project information and dependencies. `node_modules` contains the installed packages used by the project.

### What does `app.listen()` do?

`app.listen()` starts the Express server and makes it listen for requests on the specified port.

### What do `request` and `response` represent?

`request` contains information about the incoming request. `response` is used to send a result and status code back to the client.

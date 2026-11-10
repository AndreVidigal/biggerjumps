# Personal Website

Static personal site with a homepage, a small Castle Defense game, and an “A book a day” page.

## Prerequisites

- [Node.js](https://nodejs.org/) (includes `npm`)

## How to run

From the project root (`PersonalWebsite/`):

```bash
npm install
npm start
```

Then open:

- Homepage: [http://localhost:3000/](http://localhost:3000/) (or [index.html](http://localhost:3000/index.html))
- Game: [http://localhost:3000/game.html](http://localhost:3000/game.html)
- A book a day: [http://localhost:3000/abookaday.html](http://localhost:3000/abookaday.html)

`npm start` serves the site over HTTP on port 3000. Do **not** open the HTML files directly from Finder (`file://…`) — pages that load JSON (like `abookaday.html`) will fail because of browser CORS rules.

### Alternative (no npm scripts)

```bash
python3 -m http.server 3000
```

Then open the same URLs as above.

## Project structure


| Path                      | Description                                            |
| ------------------------- | ------------------------------------------------------ |
| `index.html`              | Homepage                                               |
| `game.html`               | Castle Defense game                                    |
| `abookaday.html`          | Book of the day page (loads `bookaday/book_list.json`) |
| `styles.css`              | Shared styles                                          |
| `assets/`                 | Images, fonts, sprites                                 |
| `bookaday/book_list.json` | Book list data for the book page                       |
| `package.json`            | Local server scripts (`npm start` / `npm serve`)       |




## Available npm scripts

```bash
npm start   # serve the site at http://localhost:3000
npm serve   # same as npm start
```


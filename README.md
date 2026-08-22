# Wanderlust

Wanderlust is a server-rendered accommodation listings and reviews platform built with Node.js, Express, MongoDB, and EJS. Authenticated users can create, edit, and delete their own listings with an uploaded image and a geocoded location; any logged-in user can leave a rating and comment on a listing. There is no booking, reservation, availability, or payment functionality — listings are browsed and reviewed, not booked.

---

## Live Demo

https://wanderlust-zba2.onrender.com/listings

---

## Try It Out

No signup needed — log in with the shared demo account:

- **Username:** `demo`
- **Password:** `demo`

This is a shared account. Any listing or review you create with it is visible to everyone else using the demo, and may be edited or deleted by other visitors.

---

## Tech Stack

Dependencies as listed in `package.json`:

- Express 5, Node.js
- MongoDB via Mongoose
- EJS templating via `ejs-mate`
- Passport / `passport-local` / `passport-local-mongoose` — session-based authentication
- `express-session` + `connect-mongo` — session store in MongoDB
- `connect-flash` — flash messages
- Joi — server-side validation
- Multer + `multer-storage-cloudinary` + `cloudinary` — image upload and hosting
- `@mapbox/mapbox-sdk` — forward geocoding for listing locations
- `method-override`, `body-parser`, `cookie-parser`, `dotenv`

---

## Features

**Listings**
- Create, edit, delete, and browse listings (owner-only edit/delete)
- Image upload to Cloudinary via Multer
- Location is forward-geocoded through Mapbox and stored as GeoJSON on the listing
- Text search across title, location, and country (`?search=` query param)

**Reviews**
- Add a star rating and comment to a listing
- Delete your own reviews
- Deleting a listing cascades to delete its reviews

**Authentication & Authorization**
- Signup, login, logout via Passport local strategy
- Session-based auth, sessions stored in MongoDB
- Only a listing's owner can edit or delete it; only a review's author can delete it

**Category filters and tax toggle are cosmetic only:**
- The category chips (Trending, Rooms, Beach, etc.) above the listings grid only toggle a CSS `active-filter` class on click — they do not filter the listings shown.
- The "Display total after taxes" switch toggles the visibility of a fixed `+18% GST` string next to the price — it does not calculate tax from the actual price.

---

## Local Setup

**Prerequisites**
- Node.js 20.19.2 (per `package.json` `engines`)
- A MongoDB connection string (Atlas or local)
- A Cloudinary account (cloud name, API key, API secret)
- A Mapbox access token

**Install**

```bash
git clone https://github.com/Noobod/wanderlust.git
cd wanderlust
npm install
```

**Environment variables**

Copy `.env.example` to `.env` and fill in every value:

```ini
CLOUD_NAME=
CLOUD_API_KEY=
CLOUD_API_SECRET=

MAP_TOKEN=

ATLASDB_URL=

SECRET=
```

- `CLOUD_NAME`, `CLOUD_API_KEY`, `CLOUD_API_SECRET` — Cloudinary credentials, read in `cloudConfig.js`
- `MAP_TOKEN` — Mapbox access token, read in `controllers/listing.js`
- `ATLASDB_URL` — MongoDB connection string, read in `app.js`
- `SECRET` — session/cookie signing secret, read in `app.js`

**Run**

```bash
npm start
```

This runs `node app.js`. The server listens on port `8080` (hardcoded in `app.js`, not configurable via env var).

`npm test` is currently a placeholder (`echo "Error: no test specified" && exit 1`) and will fail — there is no test suite yet.

---

## Known Limitations

- No booking, reservation, or availability system
- No payment integration
- No automated tests — `npm test` is a failing placeholder, not a real test suite
- No Docker setup
- No CI/CD pipeline
- No CSRF protection
- No pagination — listing and search queries load all matching documents at once
- No database indexes defined on any model
- No cleanup of replaced Cloudinary assets — updating a listing's image uploads a new file but does not delete the one it replaces, so orphaned images accumulate in Cloudinary

---

## License

This project was built for learning purposes and to demonstrate full-stack software engineering concepts.

# HEU-keep Deployment Guide

## 1. Frontend

This project is primarily static on the frontend side.
You can run it locally with any static file server.

### Option A: Open directly
Open either:
- `index.html`
- `liquid.html`

### Option B: Use a local static server
Example:

```bash
cd HEU-keep
python3 -m http.server 8080
```

Then visit:
- `http://127.0.0.1:8080/index.html`
- `http://127.0.0.1:8080/liquid.html`

## 2. Backend

The backend provides the track-generation API.

### Install dependencies

```bash
pip install numpy matplotlib flask flask_cors
```

### Start backend

```bash
python Json2Png.py
```

Default address:
- `http://127.0.0.1:5000`

## 3. Integration

The frontend can still be used without backend support for:
- manual drawing
- preset/local behavior
- most visual editing workflows

But the dedicated generated-track flow depends on the backend API.

## 4. Production / Demo Suggestions

### Frontend hosting options
- GitHub Pages
- Vercel static hosting
- Netlify
- Nginx / Apache

### Backend hosting options
- PythonAnywhere
- Render
- Railway
- VPS + Gunicorn / Nginx

## 5. Recommended Packaging for Demo

For portfolio/demo use, expose:
- one stable frontend URL
- one backend API URL
- a short README section showing how they connect

## 6. Operational Notes

- Ensure CORS is enabled if frontend and backend use different origins.
- Use static asset compression for images if hosting publicly.
- Add API URL configuration if backend address becomes non-local.

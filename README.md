# Beijing ↔ Seoul Live Flight Radar

A real-time dashboard showing aircraft on the Beijing ↔ Seoul corridor,
built on top of the [airplanes.live](https://airplanes.live) community
ADS-B network.

## Deploy to GitHub Pages (one-time setup)

1. **Create a new GitHub repo** at https://github.com/new
   - Name: `peksel-radar` (or whatever you want)
   - Public
   - **Do not** initialize with README / .gitignore / license
2. Run from this directory:

   ```bash
   cd ~/projects/peksel-dashboard
   git init
   git add .
   git commit -m "initial dashboard"
   git branch -M main
   git remote add origin git@github.com:YOUR_USERNAME/peksel-radar.git
   git push -u origin main
   ```
3. **Enable GitHub Pages**:
   - Repo → Settings → Pages
   - Source: `Deploy from a branch`
   - Branch: `main`, folder: `/ (root)`
   - Save. GitHub will print a URL like `https://YOUR_USERNAME.github.io/peksel-radar/`
4. **Use that URL** in the weili.io blog post's `<iframe src="...">`.

## Files

- `frontend/index.html` — the dashboard, single file, no build step.
- `README.md` — this file.

No build step, no dependencies to install, no API keys required.
The dashboard fetches data directly from `api.airplanes.live` (which
has CORS enabled for free, no-auth, public access).

## Local preview

```bash
cd frontend
python3 -m http.server 8000
# then open http://localhost:8000
```

# WASSCEPASSCO — Interactive Edition

This version is deliberately **static-host friendly**: upload the files to GitHub `main` and use GitHub Pages **Deploy from a branch**. There is no GitHub Actions workflow.

## What's included
- The actual 11 PDFs from the supplied WASSCE-Study1 project.
- Search, filters, save buttons and download/open actions.
- Interactive quick practice with saved results.
- PWA manifest, service worker and install prompt.
- Local demo sign-up/sign-in so the UI can be tested immediately.
- Real Supabase sign-up/sign-in, Google OAuth, saved resources and admin uploads when configured.
- Admin-only upload/delete dashboard.
- Privacy, Terms and About pages.
- AdSense-ready placement without fake publisher code.

## Important: why cloud sign-up needs one connection
A browser cannot create a real cloud user database by itself. To activate real accounts, create a Supabase project, run `sql/schema.sql`, then put the project's URL and public/publishable/anon key in `config.js`. Do **not** put a service_role/secret key in this project.

## GitHub Pages one-time deployment
1. Extract this ZIP.
2. Upload the contents to the `main` branch of `wasscepassco`.
3. GitHub → Settings → Pages.
4. Source: **Deploy from a branch**.
5. Branch: **main**, folder: **/ (root)**.
6. Save.
7. Open the generated Pages URL.

## Supabase
1. Create a Supabase project.
2. SQL Editor → paste/run `sql/schema.sql`.
3. Create a normal student account on the website.
4. In Supabase Table Editor → profiles, change that account's role to `admin`, or run the commented SQL using its UUID.
5. Enable Google under Authentication → Providers if desired. Configure the Google OAuth redirect/callback values using the URLs Supabase provides.
6. Put the Project URL and publishable/anon key into `config.js`.
7. Reload the website. The badge should change from Local demo mode to Cloud backend connected.

## Adding new questions after setup
Use **Admin dashboard → Upload & publish**. The PDF goes to Supabase Storage and the metadata goes into the database. No GitHub redeployment is required for each new PDF.

## AdSense
The ad slot is a placeholder only. Add Google's exact official AdSense code after an eligible account is approved. Do not invent a publisher ID or claim ads are active before configuration.

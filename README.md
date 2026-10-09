# Shadat Hossain — Interactive IT Portfolio

## Included
- Animated portfolio with floating headings/orbital hero design.
- Cursor ring that follows the mouse and expands over interactive controls.
- Project category filters and case-study popups.
- Admin login, ticket inbox/status updates, note editor and learning-path editor.
- Contact form with name, email and issue description.
- Supabase SQL schema with allow-listed admin access and row-level security.

## Backend setup is required
GitHub Pages hosts static files; it does not itself provide secure authentication or database storage. This package uses Supabase for the backend. Login, ticket persistence and admin editors remain disabled until configured.

1. Create a Supabase project at https://supabase.com.
2. Open SQL Editor and run `supabase_schema.sql`.
3. In Authentication > Users, manually create your one admin user. Do not enable public sign-up.
4. Copy that user UUID and run `insert into public.admin_users(user_id) values('PASTE-AUTH-USER-UUID-HERE');`.
5. In `script.js`, set `SUPABASE_URL` and `SUPABASE_ANON_KEY` to the project's URL and publishable/anon key. Never place a service-role key or password in browser code.
6. Test that a signed-out visitor can submit a ticket but cannot read tickets or write notes. Review RLS policies before production.
7. Upload `index.html`, `style.css`, `script.js`, and `supabase_schema.sql` to your GitHub repo. Go to Settings > Pages > Deploy from a branch > `main` > `/ (root)`.

For a user site, name the repository `USERNAME.github.io`; a project site normally publishes at `https://USERNAME.github.io/REPOSITORY/`.

## Before publishing
Verify dates, metrics, certification status, academic details and all project claims. Vendor training should not be presented as an earned certification unless it was awarded. Public learning cards are starter examples; the admin database editors are wired, but if you want new database paths to render immediately in the public learning section, connect the public read query/render step before production. Email notifications are not configured; tickets appear in the admin inbox.

# Words of Gratitude

A magical autumn gratitude experience for the SoloLearn community challenge. Visitors can add a name or nickname, share a short gratitude message, watch the golden reveal, and browse the community wall.

## Features

- Responsive, mobile-first autumn forest design
- Animated golden leaves and a cinematic gratitude reveal
- Name (24 characters) and message (180 characters) validation
- Safe text rendering with `textContent` (visitor input is never treated as HTML)
- Reduced-motion support and accessible form/status labels
- Preview mode works immediately using this browser's local storage
- Optional shared community wall powered by Supabase Database + Realtime

## Run it

Open `index.html` in a browser, or use GitHub Pages:

1. Open this repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select **main** and **/(root)**, then save.
4. Wait for the Pages URL to appear.

## Enable the shared live wall (Supabase)

Without Supabase configuration, the site is in **Preview mode**. Posts are saved only in the current browser and are not shared with other visitors.

1. Create a project at [supabase.com](https://supabase.com/).
2. Open the Supabase SQL Editor and run the complete script in [supabase/schema.sql](supabase/schema.sql).
3. In Supabase **Project Settings → API**, copy the Project URL and the **publishable/anon public key**.
4. In `index.html`, set `SUPABASE_URL` and `SUPABASE_ANON_KEY` near the top of the script.
5. Commit the change and redeploy GitHub Pages.

Only the public anon/publishable key belongs in frontend code. **Never** put a service-role or secret key in this repository.

### Important public-wall note

Names/nicknames and gratitude messages are public to everyone who can visit the page. Ask visitors not to submit private details. The included SQL policies allow public reading and anonymous posting, with length checks. For a larger public launch, add server-side rate limiting, spam filtering, and a moderation/reporting workflow (for example, a Supabase Edge Function) before promoting the wall widely. Client-side checks alone cannot prevent automated spam.

## Project files

- `index.html` — complete frontend
- `supabase/schema.sql` — table, row-level security policies, and Realtime setup

Made with a grateful heart.

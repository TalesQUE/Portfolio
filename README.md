# Portfolio — blog + services + affiliate site

Built with [Eleventy](https://www.11ty.dev/) (a static site generator — no database,
loads fast, totally free to host). Content is edited through a dashboard at
`/admin` powered by [Decap CMS](https://decapcms.org/), so day-to-day you'll
mostly never touch code.

## What's in here

- `src/index.njk` — homepage
- `src/blog.njk` — blog listing (auto-generated from `src/posts/`)
- `src/posts/*.md` — your blog posts (two examples included)
- `src/services.njk` — pricing / services page with Stripe buttons
- `src/resources.njk` — your affiliate links page
- `src/about.njk` — about page
- `src/css/style.css` — all styling, in one file
- `admin/` — the dashboard editor config

## 1. Try it locally (optional but recommended)

```bash
npm install
npm run serve
```

Opens at `http://localhost:8080`. Edit any `.njk` or `.md` file and it reloads live.

## 2. Put it on GitHub (free)

1. Create a free GitHub account if you don't have one.
2. Create a new repository (e.g. `portfolio`).
3. Upload everything in this folder to that repository (drag-and-drop on
   github.com works, or use `git push` if you're comfortable with git).

## 3. Deploy on Netlify (free hosting + free subdomain)

1. Go to [netlify.com](https://netlify.com) → sign up free (use your GitHub
   account to sign in, it's faster).
2. Click **Add new site → Import an existing project → GitHub** → pick your
   `portfolio` repo.
3. Build settings are already set via `netlify.toml` (build command
   `npm run build`, publish folder `_site`) — just click **Deploy**.
4. In ~1 minute your site is live at a free URL like
   `https://random-name-123.netlify.app`. You can rename this in
   **Site settings → Change site name** to something like
   `portfolio-yourname.netlify.app` — still free.

## 4. Turn on the dashboard editor (`/admin`)

This is what makes writing new posts feel like a real dashboard instead of
editing files.

1. In Netlify: **Site settings → Identity → Enable Identity**.
2. Under Identity settings, set **Registration** to "Invite only" (so
   strangers can't sign up).
3. Scroll to **Services → Git Gateway → Enable Git Gateway**.
4. Go to the **Identity** tab (top nav) → **Invite users** → invite your own
   email → accept the invite from your inbox → set a password.
5. Visit `https://yoursite.netlify.app/admin` and log in. You'll see a real
   dashboard: a "New Post" button, a form with title/date/tags/body fields,
   and a Publish button. Publishing there commits the file to GitHub and
   Netlify auto-rebuilds the live site in the background — no code involved.

## 5. Connect payments (free to set up)

1. Create a free account at [stripe.com](https://stripe.com).
2. Go to **Payment Links → New** and create one for each service package.
3. Open `src/services.njk` and replace each
   `https://buy.stripe.com/REPLACE_WITH_YOUR_LINK` with the real link Stripe
   gives you.
4. Stripe takes a small % per transaction only when you actually get paid —
   no monthly fee.

## 6. Add your real content

- `src/about.njk` — swap in your real bio.
- `src/services.njk` — edit prices/packages, and your email address.
- `src/resources.njk` — replace the 3 example tools with your real affiliate links.
- Delete the two example posts in `src/posts/` once you've written your own
  (or just leave them as a formatting reference).

## Later: a custom domain

`yoursite.netlify.app` is free forever and works fine to start. If you later
want `yourname.com`, that's the one part that costs money (~$10–15/year from
any registrar) — buy it, then in Netlify go to **Domain settings → Add
custom domain** and follow the DNS steps. Everything else about the setup
stays the same.

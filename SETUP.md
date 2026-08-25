# Your new site, with an admin panel

This is your site rebuilt as a Jekyll site (still plain HTML/CSS — same look,
same URLs, same photos and poems) plus an admin panel at `/admin` that lets
you edit text and swap images without touching code.

## What changed
- Every page keeps its original design and JavaScript exactly as-is.
- Editable content (bio text, photos, publications, gallery, skills,
  experience, poems, articles) now lives in small data files instead of
  being hardcoded in the HTML.
- I found the "Send Message" button on your Contact page was broken (the
  script was cut off mid-function in the repo) — fixed it so it opens a
  pre-filled email to you instead.
- I could not read your real email address (it was Cloudflare-obfuscated in
  the HTML) — I put in a placeholder `contact@imnayon.dev`. **Change this
  first thing**, in the admin panel, on the About and Contact pages.

## One-time setup (about 15–20 minutes)

### 1. Push this to a new GitHub repo
Create a new repo (e.g. `imnayon-site`) and push everything in this folder
to it. This can replace your old repo's content, or live in a new one —
your call.

### 2. Connect it to Netlify
- Go to netlify.com → **Add new site → Import an existing project**
- Pick your GitHub repo
- Build command: `bundle exec jekyll build` (already set in `netlify.toml`)
- Publish directory: `_site` (already set)
- Click **Deploy**

Your site will be live at something like `random-name-123.netlify.app`.
You can rename this in **Site settings → Change site name**, or attach your
own domain later.

### 3. Turn on Identity + Git Gateway (this is what makes login work)
In your Netlify site dashboard:
- **Site configuration → Identity → Enable Identity**
- Under Identity settings, set **Registration** to "Invite only" (so
  strangers can't sign up)
- **Site configuration → Identity → Services → Git Gateway → Enable Git
  Gateway**
- Go to the **Identity** tab → **Invite users** → invite your own email
- Check your email and accept the invite (this sets your admin password)

### 4. Update the admin config with your real site URL
Open `admin/config.yml` in your repo and replace both
`YOUR-SITE-NAME.netlify.app` with your actual Netlify URL from step 2.
Commit that change (or edit it directly in GitHub's web editor).

### 5. Log in and edit
Go to `https://your-site.netlify.app/admin`, log in with the email/password
from step 3, and you'll see a panel with sections for Home, About, Contact,
Skills, Experience, Education, Research Interests, Publications, Gallery,
Poems, and Articles. Edit any field, hit **Publish**, and Netlify rebuilds
the live site automatically within about a minute.

## What you can now do without touching code
- Swap your profile photo or banner image
- Edit your bio, department, quote, stats
- Add/remove/reorder publications
- Add/remove/reorder gallery photos (drag in a new image, pick a category)
- Add new poems or articles
- Update skills percentages, tags, timeline, conferences
- Edit all your contact details

## What's unchanged (still needs a code edit, rarely touched)
- Visual design / layout / colors — this is CSS, not content, so it stays
  as code on purpose
- The comment system on poems (still browser-local via localStorage, same
  as before — comments aren't shared between visitors, just like your
  original site)

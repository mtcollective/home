# M&T Collective — website

## What's in this folder
- `index.html`, `blog.html`, `post.html` — the site's three pages
- `content/site.json` — every editable piece of homepage text and image path
- `content/posts.json` — every blog post
- `admin/` — the content dashboard (Decap CMS)
- `netlify.toml` — tells Netlify this is a plain static site, no build step

You never need to open or edit any `.html` or `.json` file directly once
this is live — everything in `content/` is editable from `/admin`.

## One-time setup

**1. Put this folder on GitHub**
Create a free GitHub account, create a new repository, and upload every
file in this folder to it (drag-and-drop upload works fine for a first
push — GitHub's website supports it directly, no command line needed).

**2. Connect it to Netlify**
Sign up at netlify.com (free), choose *Add a new site → Import an
existing project*, and pick the GitHub repository you just created.
Leave the build settings as they are (no build command, publish
directory `.`) and deploy. You'll get a temporary netlify.app address —
the site is now live there.

**3. Turn on Identity**
In the Netlify dashboard for this site: *Site configuration → Identity
→ Enable Identity*.

**4. Turn on Git Gateway**
Still under Identity settings: scroll to *Services → Git Gateway →
Enable Git Gateway*. This is what lets the dashboard save your edits
back to GitHub.

**5. Invite yourself as a user**
Identity tab → *Invite users* → enter your own email. You'll get an
email with a link — click it, set a password. That's your login for
`/admin` from now on.

**6. Point your domain at Netlify**
Site configuration → Domain management → Add a custom domain → enter
your domain. Netlify will show you the DNS records to add at your
registrar (Namecheap, Cloudflare, etc.) — usually one A record and a
CNAME. Once added, it can take up to 24 hours to fully propagate, but
often works within minutes.

Once steps 1–6 are done, editing is simple:

## Editing the site day-to-day

1. Go to `yourdomain.com/admin`
2. Log in with the email/password from step 5
3. Pick **Homepage** to edit hero text, stats, bios, services, process
   steps, or the Instagram section — or **Blog Posts** to add, edit, or
   remove a post
4. Click **Publish** on any change — the live site updates automatically
   within a minute or two, no further action needed

To add a photo (your headshot, Duncan's, Instagram tiles), use the
image field in the relevant section — it uploads directly, no need to
name files or find a folder.

## Adding a brand-new page later

Duplicate `blog.html`, rename it, edit its content directly (it isn't
wired into the CMS unless you also add it to `admin/config.yml` — happy
to help with that when you get there), and add one link to it in the
`<nav class="top-nav">` block near the top of `index.html`, `blog.html`,
and `post.html` so it shows up site-wide.

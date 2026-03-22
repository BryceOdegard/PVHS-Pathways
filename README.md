# CTE Career Sequences — Setup Guide

## What's in this folder

| File | What it is |
|------|-----------|
| `index.html` | The live website |
| `content.json` | **All your editable content** — text, links, courses, careers, financial aid |
| `admin/index.html` | The CMS login page |
| `admin/config.yml` | Tells the CMS what fields to show |
| `netlify.toml` | Netlify configuration |

---

## One-time setup (about 20 minutes)

### Step 1 — Create a free GitHub account
Go to **github.com** and sign up if you don't have an account.

### Step 2 — Upload your site files to GitHub
1. Click the **+** button (top right on GitHub) → **New repository**
2. Name it `cte-sequences` (or anything you like)
3. Keep it **Public**, click **Create repository**
4. On the next screen, click **uploading an existing file**
5. Drag in ALL the files from this folder (keep the `admin` folder structure)
6. Click **Commit changes**

### Step 3 — Connect to Netlify
1. Go to **netlify.com** → sign up free with your GitHub account
2. Click **Add new site** → **Import an existing project** → **GitHub**
3. Select your `cte-sequences` repository
4. Leave all settings as default → click **Deploy site**
5. Your site will be live at a URL like `random-name.netlify.app`
   - You can change this to a custom name under **Site settings → Domain management**

### Step 4 — Enable Netlify Identity (for the CMS login)
1. In Netlify, go to **Site configuration → Identity**
2. Click **Enable Identity**
3. Scroll down to **Registration** → set to **Invite only**
4. Scroll down to **Services → Git Gateway** → click **Enable Git Gateway**
5. Go to **Identity** tab → click **Invite users** → enter your email
6. Check your email and accept the invite — set a password

### Step 5 — Log in to your editor
1. Go to `yoursite.netlify.app/admin`
2. Log in with the email and password you just set
3. You'll see the CMS editor — you're ready to make changes!

---

## How to edit content

Once logged in at `/admin`, you'll see two sections:

**Site Content** — Edit the hero headline, subtitle, and footer text in English and Spanish.

**Career Sequences** — Edit each of the 8 programs. For each program you can change:
- Program title and description (English and Spanish)
- Course names
- Post-secondary pathways — including an optional **link URL** to the school or credential website
- Career opportunities — job titles, salaries, and growth rates
- Financial aid — names, descriptions, and optional **link URLs** to application pages

After saving any change, Netlify will automatically rebuild and publish your site within about 60 seconds.

---

## Adding links

In the CMS, any field labeled **"Link URL (optional)"** accepts a full URL like:
```
https://studentaid.gov
```
Leave it blank if you don't want a link. When filled in, a small **↗ Learn more** button will appear on the live site next to that item.

---

## Troubleshooting

**Site isn't updating after I save?**
Check the **Deploys** tab in Netlify — it shows build status. Usually takes under 60 seconds.

**Forgot my CMS password?**
Go to `yoursite.netlify.app/admin` and click "Forgot password."

**Want to invite another editor?**
In Netlify → Identity → Invite users. Each person gets their own login.

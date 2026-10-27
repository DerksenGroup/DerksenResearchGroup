# Derksen Research Group website

Plain HTML and CSS, hosted free on GitHub Pages. There is no build step: what's in this repository is exactly what visitors see.

## Files

| File | Page |
|---|---|
| `index.html` | Home |
| `research.html` | Research |
| `our-team.html` | Current members |
| `alumni.html` | Former members |
| `publications.html` | Publication list |
| `news.html` | News posts |
| `group-photos.html` | Photo gallery |
| `positions.html` | Join us |
| `contact-us.html` | Contact |
| `support.html` | Donations and partners |
| `darren-derksen.html` | PI profile |
| `css/style.css` | All styling (colours are at the top) |
| `img/` | All images |

`copy-of-alumni.html`, `links.html` and `research-blog.html` only forward old Wix addresses to the new pages. Leave them in place.

## Common edits

You can make all of these in the GitHub website: open the file, click the pencil icon, edit, then click **Commit changes**. The live site updates within a few minutes.

**Add a team member.** In `our-team.html`, copy an existing `<article class="person">` block, paste it where the person should appear, and change the name, role and image path. Put a portrait in `img/team/` named like `first-last.jpg`, ideally cropped to 4:5 (for example 640 × 800 px) and under about 300 KB.

**Move someone to alumni.** Delete their block from `our-team.html`, then copy an `<li class="alum">` block in `alumni.html` and fill it in. Square photos (360 × 360 px) go in `img/alumni/`. If there's no photo, use the initials block instead:
`<div class="mono" aria-hidden="true">AB</div>`

**Add a publication.** In `publications.html`, copy an `<li class="pub">` block to the top of the right year. If the year is new, copy a whole `<section class="year">` and add the year to the jump list at the top. To add a TOC graphic, put it in `img/pubs/` and keep the `<figure>` line. If there's no graphic, delete the `<figure>` line and change `class="pub"` to `class="pub no-fig"`.

**Add a news post.** In `news.html`, copy an `<article class="post">` block to the top. To show it on the home page, update the news list in `index.html`.

**Add gallery photos.** Put the image in `img/gallery/` (about 1600 px on the long edge) and add a line to `group-photos.html`.

## Publishing (first time)

1. Upload every file and folder in this repository to the `ORG.github.io` repo, using **Add file → Upload files**.
2. Go to **Settings → Pages**, set **Source** to *Deploy from a branch*, then pick `main` and `/ (root)`.
3. The site appears at `https://ORG.github.io` within a few minutes.

## Moving derksenresearchgroup.com over from Wix

Do this only after the new site is checked and approved. Follow the order below: GitHub's instructions say to add the domain in GitHub first, then change DNS.

1. In this repo, go to **Settings → Pages → Custom domain**, enter `www.derksenresearchgroup.com`, and save. GitHub adds a `CNAME` file.
2. Wherever the domain's DNS is managed (probably Wix, if the domain was bought through Wix), remove the Wix records and add:
   - A `CNAME` record for `www` pointing to `ORG.github.io`
   - Four `A` records for `@` pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153` and `185.199.111.153`
3. Wait for DNS to update (up to 24 hours), then tick **Enforce HTTPS** on the Pages settings page.
4. Cancel the Wix plan, but keep the domain registration itself paid.

Reference: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

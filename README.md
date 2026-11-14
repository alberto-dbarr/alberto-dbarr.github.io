# Alberto Barragan personal site

Edit index.html in a text editor (VS Code works well). Search for "EDIT:" to find every part you can change.

## Files to add before sharing

Put these in the **photos** folder (exact names):

| File | Where it shows up |
|---|---|
| me.jpg | Your photo in About (already added: the summit shot) |
| Photography gallery | Already filled in (blue-angels.jpg, space-needle-night.jpg and more). To add one, drop it in photos and copy a figure line in index.html |
| project-nfc-card.jpg | NFC card project popup |
| project-sarp.jpg | SARP project popup (a SolidWorks screenshot of the nose cone works great) |
| project-flying-wing.jpg | Flying wing project popup |
| project-flight-endurance.jpg | Flight endurance aircraft popup |

**resume.pdf** is already in the main folder. Replace it with a new file of the same name when you update your resume.

Tips:
- Keep each photo under about 1 MB (export at around 2000 px wide, JPG quality 80).
- For every photo, change its alt="..." text in index.html to a short real description,
  like "Aerial shot of a construction site in Bellevue".

## Connect the contact form (5 minutes)

The form sends messages to your Gmail through Formspree, so your email address
never appears on the website.

1. Go to formspree.io and sign up with barragan7025@gmail.com. Confirm the email they send you.
2. Click "New Form", name it "Website contact", and create it.
3. Formspree shows an endpoint like https://formspree.io/f/abcdwxyz. Copy the last part (abcdwxyz).
4. In index.html, search for YOUR_FORM_ID and replace it with that ID.
5. Upload index.html to GitHub, then send yourself a test message from the live site.
   The first message may ask you to confirm in your inbox.

The free plan has a monthly message limit, which is plenty for a portfolio site.

## Before you share the link

1. **Boeing wording:** check your intern guidelines or ask your supervisor that the
   Boeing bullets in the Resume section are OK to post publicly.
2. **Skills:** the lists in the Resume section are a starting point. Add every tool you
   really use (SolidWorks, CATIA, Excel, etc.) and remove anything you don't.
3. **Phone test:** once the site is live, open it on your phone and tap every link,
   button and project popup.

## Custom domain (Cloudflare + GitHub Pages)

1. Buy the domain in Cloudflare (Domain Registration > Register Domains).
2. In Cloudflare DNS, add four A records for @ pointing to
   185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153,
   and a CNAME for www pointing to alberto-dbarr.github.io.
   Set all of them to "DNS only" (gray cloud).
3. In GitHub: repo Settings > Pages > Custom domain, type your domain, Save,
   then tick "Enforce HTTPS" once it's available.
4. In index.html, search "og:url" and change alberto-dbarr.github.io to your domain
   in the og:url and og:image lines.

## The connect. link for your NFC business card

This is the link that goes on the card's NFC chip and QR code, so you can change
where it points later without reprinting cards.

1. Cloudflare DNS: add a record. Type AAAA, Name connect, IPv6 address 100::,
   Proxy status ON (orange cloud).
2. Cloudflare: Rules > Redirect Rules > Create rule.
   - When incoming requests match: Hostname equals connect.yourdomain.com
   - Then: Static redirect to https://yourdomain.com (or your LinkedIn),
     status code 302, and turn on "Preserve query string" if you want.
3. Deploy, then test by visiting connect.yourdomain.com.

## Visitor stats (free, once your domain is on Cloudflare)

1. In Cloudflare, go to Analytics & Logs > Web Analytics > Add a site, and enter your domain.
2. Cloudflare gives you a short script tag. Paste it in index.html right above `</body>`.
3. After a day you can see visits and where they came from (LinkedIn, your NFC card, Google).

## Sharing one project

Each project has its own link: add #nfc-card, #sarp or #flying-wing to the end of your
site address and it opens straight to that project. The popup also has a "Copy link" button.
New projects get a link from their id="..." in index.html.

## Updating the site later

Edit index.html, then upload it again to the alberto-dbarr.github.io repo on GitHub
(or click the file on GitHub, press the pencil icon, edit, and Commit changes).
Changes go live in about a minute.

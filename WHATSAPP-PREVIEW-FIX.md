# Johanett website: WhatsApp preview correction

Production domain: https://johanett-janse-van-rensburg-associa.vercel.app/

Root causes identified before repair:
- Open Graph image and canonical URLs incorrectly used `https://johanett-janse-van-rensburg-associates.vercel.app/` (a domain not assigned to this project).
- Deployment protection included production domains, preventing public access by social-preview crawlers. The project's authentication scope was changed to preview-only via Vercel settings.
- `robots.txt` blocked all crawlers. Now explicitly allows Meta's social-preview user agents, but still prevents general crawlers.

Changes in this ZIP:
- Correct full absolute production URLs in OG, Twitter, canonical, structured data, and sitemap across all nine HTML pages.
- Every page points to `/assets/jjvr-whatsapp-preview-v2.jpg` to bust social-preview image caches.
- `og:image:secure_url` and `og:image:type` added to each page.
- 1200x630 JPEG image remains the original approved composite (firm logo + Johanett portrait).
- `robots.txt` updated for social crawlers.

After GitHub push + Vercel production deployment reaches READY, check these two URLs in a private browser:
- https://johanett-janse-van-rensburg-associa.vercel.app/
- https://johanett-janse-van-rensburg-associa.vercel.app/assets/jjvr-whatsapp-preview-v2.jpg

Then paste https://johanett-janse-van-rensburg-associa.vercel.app/ into a new WhatsApp message, wait for preview image to load, and confirm logo and Johanett photo display. WhatsApp may cache older previews; if so use Meta Sharing Debugger to scrape the URL again and retry in a new chat.

No site design/layout or contact details modified.

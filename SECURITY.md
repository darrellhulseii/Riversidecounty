# Security Policy

This repository holds the public website for Complete Home Today LLC (completehomellc.com): static HTML pages served by GitHub Pages. There is no server code or database here.

## Reporting a problem

If you find a security or privacy issue on the site — for example a way to misuse the quote, review or hiring forms, or personal information that shouldn't be public — please email **darrell@completehomellc.com** with "Security" in the subject line. Please don't open a public GitHub issue for it.

Include the page, what you found and how to reproduce it. We aim to reply within 3 business days.

## What the site does to protect visitors

- **Content Security Policy** on every page limits which outside services can run scripts or receive data. The legal pages (privacy policy, terms, do-not-call policy, notice of cancellation) run no scripts at all.
- **Clickjacking guard**: the homepage hides itself if another site loads it inside a frame.
- **Form spam protection**: each form has a hidden honeypot field, rejects submissions sent faster than a person could type, and locks while sending.
- **Input cleaning**: emails, phone numbers, ZIP codes and states are format-checked; line breaks and control characters are stripped from one-line fields, and values that start like a spreadsheet formula are neutralized, so exported leads can't run code in Excel or Google Sheets.
- **Photo uploads** on the review form are limited to JPEG, PNG, WebP and HEIC images up to 5 MB, and are re-encoded in the browser before upload, which strips location and camera data. If a phone can't re-encode the photo, it is left off rather than sent with its location inside.
- **TrustedForm** (consent certificates) loads only after a visitor starts filling in a form, not for everyone who reads the page.
- **Analytics** (Google Tag Manager and Google Analytics 4) load only once real IDs are set, and default to "denied" consent until the visitor chooses in the cookie banner.

## Notes for maintainers

- The Web3Forms access key in `index.html` is a public form key by design: it can only submit forms to the inbox, not read submissions. Keep it restricted to `completehomellc.com` in the Web3Forms dashboard.
- Never commit passwords, API secrets, private keys or customer data to this repository: it is public, and anything pushed stays in its history.

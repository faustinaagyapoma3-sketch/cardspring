# CardSpring Gift-Card Exchange

A standalone front-end prototype for a manual-review gift-card exchange marketplace.

## Included flow

1. Customer chooses a card type and sees an indicative USD quote.
2. Customer applies before sending the card.
3. Customer selects a payout method: PayPal, Venmo, Cash App, or Apple Pay.
4. Customer submits basic trade details and confirms they own the card.
5. The site displays an application ID and a manual-review status message.

The current front end intentionally does **not** ask customers to type gift-card PINs or codes into a plain HTML form. In production, card evidence should be collected through an authenticated, encrypted upload endpoint with access controls, audit logs, retention limits, and fraud screening.

## Run locally

Open `index.html` directly, or serve the folder with any static web server.

## Deploy

Upload `index.html`, `styles.css`, `app.js`, and `README.md` to GitHub Pages, Netlify, Vercel, or another static host.

## Production integrations required

This prototype only demonstrates the user experience. To operate a real exchange business, add a secure backend for:

- User accounts and authenticated customer dashboard
- Trade records with statuses: submitted, reviewing, approved, rejected, paid
- Secure card-evidence uploads; never expose card codes in URLs, logs, analytics, or client-side JavaScript
- Admin review queue with role-based access control and audit trail
- Exchange-rate rules and quote expiration
- Identity, sanctions, stolen-card, and fraud screening appropriate to your jurisdiction
- Payout APIs and verification for PayPal, Venmo, Cash App, and Apple Pay where officially supported for your business/account type
- Webhook handling and reconciliation so a payout is not sent twice
- Terms, privacy notice, refund/dispute policy, age restrictions, and local licensing/compliance review

Do not promise an automatic payout until the card has passed verification and your payout provider confirms the transfer. Payment-provider availability and gift-card resale rules differ by country and platform, so confirm the current terms and legal requirements before launch.

## Verification chat test

After an application is submitted, the confirmation action opens a CardSpring verification chat. The test front end supports attaching an image/PDF filename, sending messages, and showing a simulated reviewer reply. The current chat is a browser-only prototype; connect the form to an authenticated backend, object storage, admin inbox, and realtime messaging service before handling real card evidence.

## Customer service

The header, footer, and verification-chat header include a **Customer service** link to `https://t.me/cardspring_exchange` so customers can contact your team directly on Telegram.


After submitting an application, the centered verification chat includes **Continue in Telegram**. It opens `@cardspring_exchange` with a trade-specific start parameter so the customer can upload the card and continue the conversation directly in Telegram.

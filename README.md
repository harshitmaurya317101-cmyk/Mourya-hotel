# Maurya Hotel ordering website

## Included
- Mobile responsive menu and hero poster (your supplied menu image)
- Add-to-cart, quantity changes, cart view and checkout
- Customer full name, table number, payment choice (cash, UPI, card)
- UPI deep-link to Kotak UPI ID `7039102251@kotakbank`; Paytm ID included as supplied
- Order success screen, order number, printable bill/invoice
- Node backend saves orders in `orders.json` and emails order details to `harshitmaurya317101@gmail.com` when SMTP is configured

## Run locally
Install Node.js 18 or newer, then from this folder:
```bash
npm install
npm start
```
Open http://localhost:3000

## Email setup (needed for orders to reach your email)
Set SMTP environment variables with credentials from your email provider:
- `SMTP_HOST` (e.g. your provider's SMTP server)
- `SMTP_PORT` (usually 587)
- `SMTP_USER`
- `SMTP_PASS` (use an app password, never your normal account password)
- optional `SMTP_SECURE=true` for port 465
- optional `MAIL_FROM`

Do not put SMTP passwords in index.html or publish them. Without SMTP configured, orders are saved locally on the server and email is not sent. The frontend also has a local browser demo fallback when server is not running.

## Important production notes
- This is a starter, not yet a hardened production system. Before public deployment add an admin login, persistent database, HTTPS, input validation/rate limiting, verified payment gateway integration, and realtime status updates.
- UPI link opens the payment app; it does not verify payment automatically. Card payments need a payment gateway merchant account (for example Razorpay/Paytm gateway) and backend integration.
- Menu prices are transcribed from your poster. Please check item names/prices; the poster's “Kahai Paneer B.” and “Matter Paneer” spellings are retained.
- Customer website cannot securely receive customer payment data directly; use a hosted gateway checkout.

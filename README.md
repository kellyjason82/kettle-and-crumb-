# Kettle & Crumb Order Book

An internal alpha for **Kettle & Crumb**, a café, bakery and catering business in Kilkenny with two sites and 24 staff.

**Try it live**
- Order book (single file): https://kellyjason82.github.io/kettle-and-crumb/
- Phone app version: https://kellyjason82.github.io/kettle-and-crumb/app/

## The problem

Catering orders come in by phone, email, Instagram and WhatsApp, and no one sees all four. The bakery still works from a paper diary that drivers read at 6am to load the vans. Orders go wrong and cost refunds, and allergies can be missed.

## The fix

One order book that every channel feeds, with allergies impossible to miss.

## How it works

**Inbox.** WhatsApp, email and Instagram messages in one list. One tap turns a message into an order, and the app reads the message to fill in the date, time, number of people, occasion, name, address, items and any allergies. In this alpha the inbox is simulated (see "Next phase" below).

**New order, step by step.** One question per screen, with big buttons, so anyone can take an order on the phone or at the counter:
1. Where did it come in?
2. **Allergies?** You cannot go on until this is answered. Either "No, customer confirmed", or tap each allergen from the 14 that EU rules require food businesses to declare (enforced in Ireland by the FSAI).
3. When, how many, delivery or collection.
4. Who it is for and what they want, with quick-add buttons.
5. Check it and read it back to the customer.

**Orders.** Every order shows where it is up to: **Needs confirming → Confirmed → Ready → Out for delivery / Collected**. Each step records who did it and when. Staff can send the customer a ready-written confirmation on WhatsApp or email. Every change is logged with a name and time (for example "People 40 → 50, Grace").

**6am sheet.** A big-type sheet of tomorrow's orders for the bakery and the vans. Allergies are in red and changes in yellow. Bakers tick "Made, allergy checked" and drivers tick "Loaded", and each tick is signed with their name and the time. **Tell the counter** and **Send update** send those ticks to whoever is on the phones, by WhatsApp or email.

**Who's using this device.** Each phone or PC is set to a person once, so orders, changes and ticks are signed without extra typing.

**Red means allergy.** Nothing else in the app is red.

**Run the test** plays the class test by itself: a funeral order with a nut allergy arrives on WhatsApp, is confirmed, changes from 40 to 50 people, and goes through the bakery and the van with signed ticks.

## Next phase: connecting the channels

This alpha shows the full flow with a simulated inbox. To connect live WhatsApp, Instagram and email messages so orders fill themselves in, we need the following from Kettle & Crumb:

**Accounts and access**
- **WhatsApp:** the business number used for catering, set up on WhatsApp Business, plus a verified Meta Business account so messages can flow into the order book through the WhatsApp Business Platform.
- **Instagram:** the café's Instagram switched to a professional (business) account and linked to a Facebook Page, so direct messages can come in through Instagram's messaging connection.
- **Email:** the catering inbox (for example catering@), with permission to connect it or forward orders to the order book.

**Decisions and budget**
- **One shared order book:** agreement to host the order book online, so both sites, the bakery PC and every phone see the same orders live.
- **Running costs:** sign-off for the monthly costs of the messaging connections, the shared database and any connector tool (such as Zapier or Make), costed for years two and three as Aoife requires. This is option 4 on her list.
- **Who uses it:** the staff list and the devices at each site, so everyone is set up on day one.

**Customer data**
- Allergy details are health information under GDPR. Before going live, Kettle & Crumb needs to agree how long order and allergy details are kept and who can see them.

Until then, everything else works today. Orders are saved on each device, staff press send on WhatsApp and email messages themselves, and message reading uses text matching, so staff check every field. All customers and orders are made-up sample data; use **Reset sample data** at the bottom of the page to start again.

## Two versions

- **`index.html`** is the whole order book in one file: HTML, CSS and JavaScript together, with no external libraries. It works on a phone and on a PC. The **Phone** button shows a QR code that opens the phone app.
- **`app/`** is the phone app version. It installs on the home screen with its own icon, opens full screen and keeps opening when the bakery broadband drops. On a laptop or projector it shows inside a phone frame with a QR code to scan.

Both versions save orders on the device with `localStorage`, so on the same phone they share the same orders.

## Files

```
index.html               Order book, single file
app/index.html           Phone app version
app/manifest.webmanifest App name, icon and colours for installing
app/sw.js                Keeps the app working with no connection
app/*.png                App icons
```

# COLLEGO

**Your entire college life. One app.**

## Problem Statement

Students, event organizers and college admins need one place to publish events, get them approved, discover them, register for them and look up college details. COLLEGO solves this with a single app that has separate flows for students, organizers and admins.

## Project Description

COLLEGO is a mobile-first web app built as a single HTML file. It has three roles: **Student**, **Organizer** and **Admin**.

**How it works**

1. An **organizer** creates an account and creates an event (name, description, date, time, deadline, venue, college, free or paid fee). The event is sent to the admin for approval.
2. The **admin** reviews the event and either approves it, which makes it live for students, or rejects it with a written reason that goes to the organizer as feedback.
3. **Students** see live events on their home screen and on the *Hackathons and events* page. They register through a form covering personal details, college details, individual or team participation, food preference and consent. Paid events also ask for a transaction ID and payment screenshot.
4. After registering, the student gets an event **ticket** that can be downloaded as an image and found again under *My tickets*.
5. Organizers can see who registered for their events, and admins can see registration counts.

**Features**

- Student sign-up and sign-in with a Gmail check (prototype) and password reset
- Separate organizer sign-up/sign-in and admin sign-in
- Event approval workflow with rejection feedback
- Live events on the student home screen, with deadline and fee
- Event registration form with team support and a payment step (dummy payment QR code)
- Ticket generated on a canvas and downloadable as a PNG
- Explore colleges: search a list of engineering colleges, view details (place, university, type, courses, website, about) and add star ratings and reviews
- Admin can add and edit college details
- In-app notifications for event approvals, rejections, new events to review and new registrations
- Light and dark theme
- Passwords stored as SHA-256 hashes instead of plain text
- Optional cloud sync through Firebase Realtime Database so data is shared across devices

---

## Google AI Usage

### Tools / Models Used

- [Add the Google AI tool or model you used here]

## Tech Stack used

- HTML5
- CSS3 (custom properties, light and dark theme)
- Vanilla JavaScript
- Canvas API (ticket and payment QR drawing)
- Browser `localStorage` (default data storage)
- Firebase Realtime Database over REST (optional cloud sync)
- Google Fonts (Figtree, Manrope)

### How Google AI Was Used

[Explain here how Google AI was used in your project.]

---

### GitHub repo link of the project

[Link of the github repository](https://github.com/your_user_name/your_repo_name)

## Proof of Google AI Usage

Add your proof in the `/proofs` folder.

## Screenshots

Add project screenshots in the `/screenshots` folder.

---

## Demo Video

Upload your demo video to Google Drive and paste the shareable link here (max 3 minutes). [Watch Demo](https://drive.google.com/your-video-link)

---

## Installation Steps

```bash
# 1. Clone the repository
git clone https://github.com/your_user_name/your_repo_name.git

# 2. Go into the project folder
cd your_repo_name
```

3. Open `index.html` in any modern browser. No build step, server or `npm install` is needed.
4. An internet connection is needed to load the fonts (and for cloud sync, if you enable it).

**Demo admin login**

- Email: `admin@collego.app`
- Password: `admin123`

**Try the full flow**

1. Create an organizer account, create an event and send it for approval.
2. Sign in as admin and approve the event.
3. Create a student account, register for the event and download your ticket.

**(Optional) Cloud sync across devices**

1. Create a Firebase Realtime Database.
2. In the `<script>` of `index.html`, set your database URL:
```js
   var CLOUD_URL = 'https://your-project-default-rtdb.asia-southeast1.firebasedatabase.app';
```
3. If `CLOUD_URL` is left empty, all data stays in the current browser (`localStorage`).

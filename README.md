# COLLEGO
COLLEGO is a mobile-friendly web app that puts college life in one place: attendance, timetables, notes and college search. Organizers post hackathons for admin approval, students register and get downloadable tickets, and organizers see who signed up while the admin sees only the count.
# COLLEGO

**Your entire college life. One app.**

COLLEGO is a mobile-friendly web app for college students. Its working features are a hackathon and event system with three account types (student, organizer and admin) and a college directory with reviews. The whole app is one HTML file.

---

## Accounts

| Role | What they can do |
| --- | --- |
| **Student** | Sign up, browse events approved by the admin, register for an event, get a downloadable ticket, search colleges, review events and colleges |
| **Organizer** | Create an account with a club or organization name, send events to the admin for approval, edit and resubmit rejected events, see the details of every student who registered, search colleges |
| **Admin** | Review events sent by organizers, approve them or reject them with a written reason, see the number of students registered for each live event, add and edit colleges |

The organizer sees each registered student's details. The admin sees only the number of registrations.

---

## How an event moves through the app

1. The organizer fills in the event details and clicks **Send to admin for approval**.
2. The event shows as pending. The admin gets a "New event to review" notification.
3. The admin opens the event and clicks **Approve**, or **Reject** with a reason.
4. If rejected, the organizer sees the reason, clicks **Edit and resubmit**, and sends it again.
5. If approved, the event goes live and students can see it on **Hackathons and events** until the registration deadline.
6. The student registers and receives a ticket.
7. The organizer is notified and sees the student under **Participants**. The admin's registration count goes up.

### What the organizer enters

Event name, about the event (optional), event date, event time (optional), registration deadline, venue, the college conducting the event (optional, with a search box that suggests colleges), and a registration fee (free, or paid with an amount).

---

## Student sign-up and sign-in

1. Choose **Continue with college email** and enter a Gmail address.
2. A new student then creates an account: full name, phone number, college name, course and branch, year of study, university register number, email, password and password confirmation.
3. A returning student enters their password instead.

## Event registration form

| Field | Notes |
| --- | --- |
| Full name | Required |
| Email address | Required |
| Phone / WhatsApp number | Required |
| College name | Required |
| Department and year of study | Required |
| College ID or roll number | Required |
| ID card upload | Optional |
| Taking part alone or as a team | Individual or Team. A team needs a team name and team members' details |
| Food preference | Veg or Non-Veg, required |
| Payment | Shown only when the event has a fee: a QR code, a transaction ID and a payment screenshot, all required |
| Consent | Tick box to accept the rules and code of conduct, required |

Registration closes after the event's deadline.

## Ticket

After registering, the student gets a ticket showing:

- Event name and host
- Attendee name, date, venue and time
- College, department and year, ID or roll number
- Team (or Individual) and food preference
- Payment (fee and transaction ID) or "Free entry"
- Ticket ID, a QR-style pattern and the registration date

The ticket can be downloaded as a PNG image, and it appears under **My tickets** on the events screen.

---

## Colleges

- The admin adds colleges and edits them: name, place and district, university, type of college, courses offered, website (optional) and about.
- Students, organizers and the admin can search the college list.
- Students can write a review for a college or an event.

## Home screen (student)

Sections for Your college, Explore other colleges, Hackathons and events, Attendance calculator, Exam timetable, Exam resources and Notes, plus Reminders and Suggested for you.

## Notifications

Students, organizers and the admin have a notification screen.

- **Student:** live events they have not registered for yet
- **Organizer:** approvals, rejections with the reason, and new registrations
- **Admin:** new events waiting for review

## Other features

- Password reset from the sign-in screens: enter your name, Gmail address and a new password
- Dark and light themes, saved between visits
- Responsive layout, visible keyboard focus and support for reduced motion

---

## Getting started

Open the HTML file in a web browser. The Google Fonts (Figtree and Manrope) load from the internet, with system fonts as a fallback.

### Sign in as each role

| Role | How |
| --- | --- |
| **Admin** | On the first screen choose **Organizer or admin? Sign in here**, switch to **Admin**, and use the demo login `admin@collego.app` / `admin123` |
| **Organizer** | On the same screen stay on **Organizer**, choose **New organizer? Create an account**, and enter your full name, club or organization, email and password |
| **Student** | Choose **Continue with college email** and follow the steps above |

### Try the full flow

1. As an organizer, create an event and send it for approval.
2. Sign in as admin, open the event and approve it.
3. Sign in as a student, open **Hackathons and events**, and register.
4. Sign back in as the organizer to see the participant's details. Sign in as admin to see only the count.

---

## Where the data is stored

Events, accounts, registrations and reviews are kept in the browser's `localStorage`, so all three accounts see the same data on one device.

### Optional cloud sync

The app can sync through a Firebase Realtime Database so accounts, events and registrations are the same on every device. Near the top of the script, paste your database URL between the quotes:

```js
var CLOUD_URL = '';
```

The URL looks like `https://your-project-default-rtdb.asia-southeast1.firebasedatabase.app`. Left empty, everything stays on this device only.

Each device keeps a local copy, sends the records it changed and receives the ones other devices changed. If the cloud can't be reached, the app shows a message that changes are saved on the device and will sync later.

---

## How the file is organized

Everything is in one HTML file with no frameworks and no build step:

- `<style>` at the top: colors for the light and dark themes and all component styles
- The screens in the middle: login, registration, sign-in, home, notifications, organizer and admin sections, events, event details, registration form, ticket and colleges
- One `<script>` at the bottom: navigation, forms, roles and approvals, storage, cloud sync and ticket drawing

The ticket image is drawn on an HTML canvas.

---

## Current status

**Placeholder pages.** These home screen sections open a page that says "Being set up":

- Your college
- Attendance calculator
- Exam timetable
- Exam resources
- Notes

## Prototype notes

- Passwords are hashed (SHA-256) before they are saved.
- The admin demo login is written into the file.
- Gmail verification is a prototype check: it confirms the address ends in `@gmail.com`.
- Password reset does not send an email or a code.
- The QR code shown for payment is a demo pattern, not a real payment code.
- For the ID card and payment screenshot, only the file name is saved, not the image.

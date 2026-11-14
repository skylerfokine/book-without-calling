# Book Without Calling

**Hackpalachia 2026 · Rural Health Hackathon · Care Delivery track**

A free mobile health van in rural Southeast Ohio (Meigs County). Patients book, change or cancel visits by plain text, with no phone call, no app and no data plan. Clinic staff see everything on one screen, and anything medical or unclear goes to a human.

**Live demo:** https://skylerfokine.github.io/book-without-calling/

## Views

| Link | Who it's for |
|---|---|
| `#patient` | A patient's phone. Use **texting as** to switch between Linda, Ray, Carol, Donna, Rita and Mae. Works on a real phone. |
| `#staff` | The clinic staff console: daily list, "needs a human" queue, live message feed |
| `#both` | Phone and console side by side on one screen |

## Live sync across devices

Open the patient view on a phone and the staff view on a laptop. Every patient text and every staff action shows up on both within about a second.

- Each action is a small event sent through a free public relay ([ntfy.sh](https://ntfy.sh)). Every page in the same **room** applies the same events in the same order.
- A device that joins late replays everything since the last **Reset**, so it matches right away.
- Tabs in the same browser also sync directly, so the demo still works if the relay is down. The badge in the top bar shows which mode you're in.
- Use a private room for presentations: `?room=yourcode` (or press **Start a private room** on the home page). Everyone in the default room shares one demo.

> The relay is public. Demo with fictional data only, never real patient information. A real deployment would use the clinic's own HIPAA-covered texting vendor and server.

## Built vs. mocked up

- **Built:** the text-understanding rules, booking/changing/cancelling, the waitlist auto-fill, urgent-message routing, the no-signal queue, the staff console, and cross-device sync.
- **Simulated:** real SMS delivery, automated calls, postcards, van GPS, and the Athena export (it copies a list to paste in).
- **Fictional:** all patients, the schedule, and counts. The transit phone number is a placeholder.

## Files

- `index.html`: the whole demo in one file (no build step)

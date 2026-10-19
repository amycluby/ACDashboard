# Auntie Connie's Dashboard

A one-page screen for an iPad. It reads Indiana University's football, men's
basketball and women's basketball schedules from ESPN. About 20 minutes before
a game on a Hulu channel, it shows one giant red **Watch the Hoosiers** button
that opens Hulu to that channel. On Sunday mornings it shows a blue
**Watch church** button. Nobody has to update it during the season.

## 1. Fill in the settings

Open `index.html` and edit the `SETTINGS` block at the top:

- **`huluLinks`:** paste the Hulu network-page link for each channel. Start
  with BTN, FOX, NBC, CBS, ESPN and FS1, which carry most IU games. Channels
  left blank still work: the button opens Hulu and tells her which channel to pick.
- **`church.link`, `church.start`:** the church's Facebook live link and its
  start time.

## 2. Put it online (Vercel, free)

1. In Vercel, choose **Add New → Project** and import the
   `ACDashboard` GitHub repository (Vercel project AC-Dashboard).
2. Leave every setting as it is (no framework, no build command) and click **Deploy**.
3. Copy the web address Vercel gives you.

Every change pushed to `main` goes live automatically.

## 3. Set up her iPad

1. **Test the links on her iPad first.** Open each Hulu link in Safari on her
   iPad and check that the Hulu app opens on the right channel.
2. **Add the page to her Home Screen:** open the address in Safari, tap Share,
   then **Add to Home Screen**, and name it "Hoosiers".
3. **Keep the screen on:** Settings → Display & Brightness → Auto-Lock →
   **Never**. Keep the iPad on a stand and plugged in.
4. **Optional, to bring the page up by itself:** Shortcuts app → Automation →
   New → Time of Day. Pick a time before her usual game days and set it to
   **Run Immediately**. Add the action **Open URLs** with the page's address.
   Repeat for the church start time on Sundays, using the Facebook link directly.

## What it can't do

- **Some IU games aren't on Hulu.** Games on Peacock, BTN+ or ESPN+ show as
  "not on Hulu" and don't get a button.
- **Hulu link format:** the network-page links aren't an official Hulu
  feature. If Hulu changes them, a button may open Hulu's home screen instead.
  Re-copy the link from hulu.com to fix it.
- **Wi‑Fi:** the schedule needs a connection. Without one, the page shows a
  plain message and keeps retrying.

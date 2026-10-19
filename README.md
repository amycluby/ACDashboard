# Auntie Connie's Dashboard

A one-page screen for Auntie Connie's iPad. She doesn't have to find anything:
at the right time, one big button appears, and she taps it.

- **IU games:** Indiana football, men's basketball and women's basketball. The
  schedule comes from ESPN and updates itself. About 20 minutes before a game
  on a Hulu channel, a giant red **▶ Watch the Hoosiers** button appears and
  opens Hulu on that channel.
- **Church:** Lovers Lane United Methodist Church streams both Traditional
  services live on YouTube. On Sundays a big blue **▶ Watch church** button
  appears from 8:00 to about 10:15 AM (8:15 service) and from 10:40 AM to
  1:00 PM (11:00 service). The rest of the week, a **Watch last Sunday's
  service** button opens the recordings.
- **Sports anytime:** four big tiles (Big Ten, ESPN, FS1, FOX) are always on
  screen. Each opens that channel live in Hulu, whatever is on. Change them in
  `sportsChannels`.
- **Family:** a green **✉ Message family** button is always on screen. It
  opens the iPad's Messages app, where her family's conversations are pinned at
  the top. No phone numbers are stored in the dashboard.
- **Between games:** the screen shows the next game, its time and channel, and
  the next service.

Times follow the iPad's clock (Central time for her).

---

## Part 1: Settings (whoever manages the page)

All settings are in the `SETTINGS` block at the top of `index.html`. Changes
pushed to `main` go live automatically through Vercel.

| Setting | What it is |
|---|---|
| `huluLinks` | One Hulu link per TV channel (see below). |
| `huluFallback` | Used when a channel has no link: opens Hulu's home screen, and the button tells her which channel to pick. |
| `church.link` | Live stream: `https://www.youtube.com/@LlumcOrg/live` |
| `church.recordings` | Past services: `https://www.youtube.com/@LlumcOrg/streams` |
| `church.starts` | Service times, 24-hour clock: `08:15`, `11:00` |
| `sportsChannels` | The always-on "Watch sports now" tiles. Each uses that channel's link from `huluLinks`. Keep it to about four. |
| `messagesLink` | `messages://` opens the Messages app. If that doesn't work on her iPad, use `sms:` (opens a new message instead). `""` hides the button. |
| `showMinutesBefore` | How early a button appears (20 minutes). |

### Getting the Hulu channel links

All 13 channels are filled in. To replace one if it ever stops working:

1. On a computer, go to hulu.com and sign in with her account.
2. Open **Live** and start the channel playing. For FOX, NBC, CBS and ABC,
   pick her local station (the one with local call letters).
3. Copy the address from the address bar. It looks like
   `https://www.hulu.com/watch/...`.
4. Paste it into `huluLinks` next to the channel's name.
5. **Test it on her iPad:** open the link in Safari. The Hulu app should open on
   that channel, live.

Games on Peacock, BTN+ or ESPN+ aren't on Hulu. The page lists them as
"not on Hulu" and doesn't show a button for them.

### Hosting (Vercel)

The project is the Vercel project **AC-Dashboard**, connected to the
`ACDashboard` GitHub repository, `main` branch. No build settings are needed.
Write the page's web address here once you have it:

> Dashboard address: `https://____________________`

---

## Part 2: Setting up her iPad

Do this with the iPad in hand, ideally in one sitting. Plan about 45 minutes.

### A. Basics

1. **Clock:** Settings → General → Date & Time → **Set Automatically: On**.
   Check that it shows Central time.
2. **Screen stays on:** Settings → Display & Brightness → Auto-Lock → **Never**.
   Keep the iPad on a stand and plugged in.
3. **Bigger, bolder text:** Settings → Display & Brightness → turn on
   **Bold Text** and move **Text Size** most of the way up.
4. **Updates:** Settings → General → Software Update → turn on Automatic Updates.
5. **Wi‑Fi:** make sure it joins her home Wi‑Fi automatically.

### B. Apps and sign-ins

1. Install **Hulu** and **YouTube** from the App Store.
2. **Hulu:** sign in. If it asks "Who's watching?", pick her profile once.
   If you can, remove extra profiles so it doesn't ask again.
3. **YouTube:** open any video and tap **CC** to turn captions on. YouTube
   remembers this. Signing in is optional; it isn't needed to watch.

### C. Put the dashboard on the Home Screen

1. Open Safari and go to the dashboard address.
2. Tap **Share** (square with an arrow) → **Add to Home Screen**.
3. Name it **Hoosiers & Church** and tap **Add**.
4. **Put it in the Dock:** press and hold the new icon, then drag it into the
   Dock at the bottom of the screen.
5. **Tidy the Home Screen:** move other apps she doesn't use into a folder on
   the second page, or remove them from the Home Screen. Keep the dashboard,
   Messages and FaceTime where she can see them.

### D. A big Home button (AssistiveTouch)

Swiping up from the bottom is hard with stiff fingers. This adds a floating
button that takes her Home with one tap.

1. Settings → Accessibility → Touch → **AssistiveTouch: On**.
2. **Custom Actions → Single-Tap → Home.**
3. **Idle Opacity → 100%**, so the button doesn't fade.
4. Drag the floating button to a corner she can reach easily, away from the
   video controls.

### E. Bring the dashboard back automatically

When she leaves YouTube, Hulu or Messages, the dashboard opens by itself.

1. Open the **Shortcuts** app → **Automation** → **+** (New Automation).
2. Choose **App**. Select **YouTube**, **Hulu** and **Messages**, select **Is Closed**, and
   untick **Is Opened**.
3. Choose **Run Immediately**, and turn off **Notify When Run**.
4. Tap **New Blank Automation** → add the action **Open URLs** → enter the
   dashboard address.
5. **Test it:** open YouTube, tap the AssistiveTouch button. The dashboard
   should come back.

### F. Optional: open church by itself on Sunday

Use this if she isn't always in front of the iPad when the button appears.

1. Shortcuts → Automation → **+** → **Time of Day**.
2. Set **8:13 AM**, Repeat **Weekly**, **Sunday** only, and **Run Immediately**.
3. Action: **Open URLs** → `https://www.youtube.com/@LlumcOrg/live`.
4. Make a second one for **10:58 AM** if she'd rather watch the 11:00 service.

### G. Hearing and texting

1. **Live Captions:** Settings → Accessibility → **Live Captions: On**. Captions
   appear for any sound on the iPad, including FaceTime calls.
2. **Volume:** if she has Bluetooth hearing aids, pair them under Settings →
   Accessibility → Hearing Devices. Otherwise, a small Bluetooth speaker near her
   chair helps.
3. **Messages:** texting happens in the iPad's own Messages app, not on the
   dashboard.
   - Add contacts for you, her kids and her sister, each with a clear photo.
   - In Messages, press and hold each of their conversations → **Pin**. Pinned
     conversations sit at the top as large photos she can tap.
   - Drag **Messages** into the Dock next to the dashboard.
   - Show her the microphone button on the keyboard, so she can talk instead of
     type.
   - Settings → Messages → turn on **iMessage**, signed in with her Apple ID.

---

## Part 3: Test before you leave

- [ ] The dashboard opens from the Dock icon and shows the next IU game.
- [ ] Each Hulu link opens the Hulu app on the right channel.
- [ ] **Message family** opens Messages with her family pinned at the top.
- [ ] **Watch last Sunday's service** opens YouTube; tapping the AssistiveTouch
      button brings the dashboard back.
- [ ] The iPad is plugged in, on Wi‑Fi, and the screen doesn't lock.
- [ ] Sound is loud enough from her chair, and captions show on YouTube.

## Troubleshooting

| What happens | What to do |
|---|---|
| "The game schedule didn't load" | Check Wi‑Fi. The page retries every few minutes by itself. |
| The red button opens Hulu's home screen | That channel's link is missing or Hulu changed it. Re-copy it from hulu.com (Part 1). |
| No red button for a game | The game is on Peacock, BTN+ or ESPN+ (not on Hulu), or the channel isn't announced yet. |
| Church button opens YouTube but nothing is playing | The service hasn't started yet. Use **Watch last Sunday's service** later. |
| Hulu asks "Who's watching?" | Tap her profile. Removing extra profiles stops it. |
| The dashboard didn't come back after YouTube | Check the automation in Part 2 E is on and set to **Run Immediately**. |
| The screen went dark | Auto-Lock got turned back on (Part 2 A). |

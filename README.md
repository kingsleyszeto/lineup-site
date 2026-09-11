# lineup-site

The public website for the Lineup iOS app: landing page, privacy policy and
terms of service, served by GitHub Pages.

- `index.html` — landing page
- `privacy.html` — privacy policy (the URL App Store Connect requires)
- `terms.html` — terms of service

This repo is **public on purpose**, and exists separately from the app's own
repo for exactly that reason: the app repo is private and contains internal
notes and development credentials that must not be published. Nothing but
these pages belongs here.

Each page is a single self-contained file with its CSS inlined, so there is no
build step and nothing to break on deploy. Edit the HTML, push to `main`, and
Pages republishes.

## When the app ships

Two things change on the day Lineup is released:

1. `index.html` — replace the "Coming soon to iOS" badge with a link to the
   App Store listing.
2. In the **app** repo, set `INSTALL_URL` in `src/utils/inviteLink.ts` to this
   site, so invite links stop pointing nowhere for people who don't have the
   app yet.

## Privacy policy accuracy

The policy describes what the app actually stores, not boilerplate. If the app
starts collecting something new — analytics, crash reporting, location,
anything — the policy has to change **before** that ships, and the App Store
Connect privacy questionnaire and `ios/Lineup/PrivacyInfo.xcprivacy` have to
agree with it.

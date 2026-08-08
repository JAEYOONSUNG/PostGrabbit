# PostGrabbit

A desktop app that finds academic job postings, keeps them in one place, and
helps you decide which are worth an application.

It runs entirely on your own machine. There is no account, no server, and
nothing about your search leaves your computer except the requests to the job
boards themselves.

**[Download the latest release →](../../releases/latest)** · macOS (Apple
silicon)

---

## What it does

**Collects.** Around fifteen sources on a schedule you set: LinkedIn, Indeed,
Euraxess, ScholarshipDB, ResearchGate, Nature Careers, jobs.ac.uk,
AcademicPositions, Korean boards (IBRIC, HiBrain, NRF, university pages), and
individual lab websites. You choose which countries the general boards are
asked about — the academic feeds cover Europe, the UK and Korea, so everywhere
else, Australia and New Zealand included, arrives through that setting.

**Sorts.** Every posting is scored against your research interests and CV
keywords and lands in a band from A to N. Roles are a facet rather than a
guess: postdoc, PhD programme, master's, research staff and faculty are
separate searches, and picking one changes what gets collected, not just what
gets shown.

**Reads the advert for you.** Pay, contract length, visa terms and eligibility
are pulled out of the prose. Findings that end an application — citizenship,
clearance, no sponsorship — are separated from ones you might still meet, like
a background check, and from paperwork like badging.

**Maps it.** A globe places each posting in its city where the advert says
one, so you can see where the work actually is rather than one column per
country.

**Follows people, not only postings.** Add a PI and the app tracks their
papers, patents, topics and lab homepage, draws the network around them, and
tells you when something new appears.

**Keeps your work.** Notes per posting, an interview preparation pad, a
kanban of what you have applied to, and drag-to-order lists.

**Bilingual.** Korean and English throughout; it follows your system language
and you can switch at any time.

---

## Installing

1. Download the `.dmg` from [the latest release](../../releases/latest).
2. Open it and drag **PostGrabbit** into Applications.
3. Open it from Applications.

macOS will refuse the first launch, because this build is not notarised with
Apple. **Control-click the app and choose Open**, then confirm. You only have
to do this once.

## First run

The app opens on a setup checklist and will not collect anything until two
things are filled in:

- **Research field** — what you actually work on. Search terms are built from
  this, and it is also what postings are scored against.
- **My skills and keywords** — what is on your CV.

Then choose, on the same screen:

- **Roles to collect** — postdoc is the default. Tick PhD or master's if that
  is what you are looking for; a role you do not tick is never searched for.
- **Countries to search** — the United States by default. Tick Australia, New
  Zealand or anywhere else you would consider.

Everything else is optional and each item says which feature it turns on.

## Where your data lives

```
~/Library/Application Support/PostGrabbit/
├── data/        the database of postings, notes and watched PIs
├── config/      your profile and any API keys
├── logs/
└── outputs/     Excel exports, when you ask for one
```

Nothing is uploaded. The app talks to job boards, and to Semantic Scholar,
OpenAlex, Crossref and OpenStreetMap when you ask it to look a PI or an
institute up. Optional features (news, patents, cover-letter drafting) use
services you supply your own key for, and stay off until you do.

## Backing up

Settings has a **Data backup** card: one click writes a consistent,
compressed snapshot of the database — postings, notes, stars, watched PIs —
plus your pasted images into `Application Support/PostGrabbit/backups/`, and
shows it in Finder so you can copy it to a drive or cloud folder of your own.
Restoring is deliberately manual: quit the app, double-click the archive, put
`jobs.db` back into the `data` folder.

## Updating

The app checks this repository for a newer release and tells you in Settings.
Downloading is one click; installing is the same drag as the first time. A
backup is made automatically before every download.

**An update never touches your settings.** The application lives in
Applications and everything you own lives in Application Support — replacing
one cannot reach the other. Your profile, research field, keywords, collected
postings, notes and letters all survive.

## Requirements

- macOS on Apple silicon
- Google Chrome, if you want the app to open in its own window rather than a
  browser tab

---

## Reporting a problem

Open an issue here. A log from
`~/Library/Application Support/PostGrabbit/logs/` helps; check it for anything
you would rather not share before attaching it.

## About this repository

This holds the releases and this page. The source lives separately.

Job postings belong to the sites that publish them. The app reads public
pages, at a polite rate; it does not sign in to anything on your behalf and it
does not redistribute what it collects.

Bundled data and libraries are credited in the third-party notices shipped
inside the disk image.

<h1 align="center">Aditya Chandra Prajapati</h1>

<p align="center">
  <sub><b>PROOF OF WORK · ACP.X</b></sub>
</p>

<p align="center">
  Backend developer. I build services that run on their own and keep running.
</p>

<p align="center">
  <a href="https://air01aditya.github.io"><img src="https://img.shields.io/badge/Portfolio-air01aditya.github.io-1a1a18?style=flat-square&labelColor=fcfcfb" alt="Portfolio" /></a>
  <img src="https://img.shields.io/badge/Pune,%20India-6b6a63?style=flat-square" alt="Pune, India" />
</p>

---

A portfolio should do one thing: show the work, and show that it runs. Everything below links to source you can read. Nothing is listed until it's real.

### 🛰 JobRadar — scheduled ingestion service + Android client

**[github.com/air01aditya/JobRadar](https://github.com/air01aditya/JobRadar)** · `Python` `Kotlin` `Firestore` `GitHub Actions`

A poller runs every 15 minutes on GitHub Actions, pulls postings from five sources, normalises, filters and deduplicates them, writes to Firestore and pushes matches to a phone over FCM.

The parts worth reading:

- **Failure isolation** — each source adapter runs in its own `try/except`, so one site changing its markup doesn't take down the run
- **Two-layer dedupe** — collapses duplicates within a run, then checks a content-derived `sha256(source:source_id)` against `/seenJobIds` across runs, so a posting can never notify twice
- **Atomic writes** — new jobs land in `/jobs` and `/seenJobIds` in a single batch commit, so a crash can't mark a job seen that was never stored
- **Cold-start suppression** — an empty dedupe collection means first run; it records everything and sends nothing, instead of firing fifty notifications at once
- **Asymmetric security rules** — clients read the feed and write only their own FCM token; dedupe state is closed to them entirely. The poller uses the Admin SDK and bypasses the rules, which exist to constrain the untrusted party

### Also on the shelf

| Project | What it is | Built with |
| :--- | :--- | :--- |
| **[Night Cravings](https://github.com/air01aditya/Night-Cravings)** | Ordering app for a hostel's late-night food service — cart, WhatsApp checkout, PIN-gated owner panel, time-gated hours. No backend, no build step. | JavaScript, ES modules |
| **[MySnakeGame](https://github.com/air01aditya/MySnakeGame)** | Terminal Snake in standard C++. No engine — a hand-rolled queue tracks the body. | C++ |
| **[Patient Summary Dashboard](https://github.com/air01aditya/PATIENT-SUMMARY-DASHBOARD)** | Clinical metrics in one view. Ships the `.pbix` so you can open it yourself. | Power BI |
| **[Coffee Shop Sales Dashboard](https://github.com/air01aditya/Coffee-Shop-Sales-DashBoard)** | Sales KPIs, footfall, hourly trends and product mix. | Excel |

### Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-DD2C00?style=flat-square&logo=firebase&logoColor=white)
![SQLite](https://img.shields.io/badge/Room%20%2F%20SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

REST integration · web scraping · scheduled jobs · push notifications · relational modelling

---

<p align="center">
  <sub>Open to backend roles · Building in the open at <a href="https://air01aditya.github.io">air01aditya.github.io</a></sub>
</p>

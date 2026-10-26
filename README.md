<a href="https://madaraka.work">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.webp">
    <img src="assets/banner-light.webp" alt="Lincoln Madaraka. Software engineer, Laravel and PHP specialist, DevOps and AI automation. I build the software businesses run on." width="100%">
  </picture>
</a>

<p align="center">
  <a href="https://madaraka.work"><img alt="Portfolio: madaraka.work" src="https://img.shields.io/badge/Portfolio-madaraka.work-a9622b?style=for-the-badge&labelColor=2a1f17"></a>
  <a href="mailto:softwares.lincoln@gmail.com"><img alt="Email: softwares.lincoln@gmail.com" src="https://img.shields.io/badge/Email-softwares.lincoln%40gmail.com-a9622b?style=for-the-badge&labelColor=2a1f17"></a>
  <br>
  <a href="https://linkedin.com/in/lincolnm1"><img alt="LinkedIn: lincolnm1" src="https://img.shields.io/badge/LinkedIn-lincolnm1-a9622b?style=for-the-badge&labelColor=2a1f17"></a>
  <a href="https://x.com/lincolnmadaraka"><img alt="X: @lincolnmadaraka" src="https://img.shields.io/badge/X-%40lincolnmadaraka-a9622b?style=for-the-badge&labelColor=2a1f17"></a>
</p>

<p align="center">
  <a href="#what-i-build"><b>What I build</b></a> &nbsp;&middot;&nbsp;
  <a href="#selected-work"><b>Selected work</b></a> &nbsp;&middot;&nbsp;
  <a href="#stack"><b>Stack</b></a> &nbsp;&middot;&nbsp;
  <a href="#experience"><b>Experience</b></a> &nbsp;&middot;&nbsp;
  <a href="#lets-build-something"><b>Contact</b></a>
</p>

<br>

<p align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/stats-dark.webp">
  <img src="assets/stats-light.webp" alt="By the numbers: 6 systems written up as full case studies; 52 module packages in ERP Go; 22 staff logins in OptimaERP, one for every job; 119 automated tests behind BloodAfya." width="100%">
</picture>
</p>

<br>

I build and run production systems end to end: Laravel ERPs, internal dashboards, client platforms and the servers underneath them. Most of my work runs from database design, through deployment, to whoever has to keep it alive afterwards. Right now that means leading software and technology operations at Red Giant Media Agency in Nairobi, and building for clients on Upwork.

> **Need an ERP, a platform or an automation built?** I take it from the first conversation to the server it runs on, with support after launch. [Start a conversation &rarr;](https://madaraka.work/contact)

<br>

## What I build

<a href="https://madaraka.work/services">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/services-dark.webp">
    <img src="assets/services-light.webp" alt="Three services. 01 Custom ERP and Business Software: one system for the whole business, built around how it actually works; typically 3 to 10 months. 02 Platform and DevOps: infrastructure your engineers use without filing a ticket; typically 4 to 12 months. 03 AI Automation: AI systems that are trustworthy enough to keep in production; typically 2 to 7 months." width="100%">
  </picture>
</a>

<br>

## Selected work

> Talk is cheap. Show me the product.

<br>

### 01 &nbsp;/&nbsp; BloodAfya

<a href="https://bloodafya.madaraka.work">
  <img src="assets/showcase-bloodafya.webp" alt="BloodAfya on desktop and phone: the donor dashboard, the public home page and the mobile layout." width="100%">
</a>

<p align="center">
  <a href="https://bloodafya.madaraka.work"><img alt="Open the live app" src="https://img.shields.io/badge/Open_the_live_app-a9622b?style=for-the-badge"></a>
  <a href="https://madaraka.work/work/bloodafya"><img alt="Case study and demo logins" src="https://img.shields.io/badge/Case_study_%2B_demo_logins-2a1f17?style=for-the-badge"></a>
</p>

**A live platform that finds a compatible blood donor nearby, then reaches them by push and SMS the moment blood is needed.** Donors are ranked by ABO/Rh compatibility, distance and urgency, hospitals track their blood stock, and every channel is built so one failure never stops a match. You can sign in and try it as a donor or a recipient.

<table>
  <tr>
    <td width="50%"><img src="assets/shot-bloodafya-request.webp" alt="The I Need Blood form on BloodAfya: name, blood type, location with GPS, and urgency."><br><sub><b>Ask for blood</b>: location and urgency go in, and the matcher ranks compatible donors within 20 km</sub></td>
    <td width="50%"><img src="assets/shot-bloodafya-demo.webp" alt="The Try it yourself section of the BloodAfya case study, with shared donor and recipient logins."><br><sub><b>Try it yourself</b>: shared donor and recipient logins with a step-by-step tour</sub></td>
  </tr>
</table>

<details>
  <summary><b>How it is built</b></summary>
  <br>

- **Ranks donors the way a blood bank would.** An exact blood type ranks above a compatible one, distance is measured with the Haversine formula inside 20 km, and urgency lifts the score (1.2x high, 1.5x emergency). The scoring is a pure function with its own unit tests.
- **Three alert channels, none of them a blocker.** Web Push and SMS go out in parallel when a request is raised; push and email follow for everything after. A failed channel is logged, never thrown, so one broken gateway cannot stop a match.
- **Blood stock that follows the donations.** Hospitals track stock by lot, blood type and expiry. A completed match draws it down and warns the hospital when it runs low.
- **Keys encrypted, sessions signed.** SMS, email and push credentials are stored in PostgreSQL under AES-256-GCM, and every protected action checks the caller's role on the server.
- **A public demo that cannot reach a real person.** Test accounts only alert other test accounts, by push, and reset to a clean state every 20 minutes.
- **119 automated tests.** 110 Vitest unit tests and 9 Playwright end-to-end runs.

**Stack:** Next.js · React · TypeScript · PostgreSQL · Tailwind CSS · Web Push · Vitest · Playwright · Vercel
</details>

<br>

### 02 &nbsp;/&nbsp; ERP Go

<a href="https://madaraka.work/work/erpgo">
  <img src="assets/showcase-erpgo.webp" alt="ERP Go: the workspace overview, the sign-in page and the accounting ledger with its trial balance." width="100%">
</a>

<p align="center">
  <a href="https://madaraka.work/work/erpgo"><img alt="Read the case study" src="https://img.shields.io/badge/Read_the_case_study-a9622b?style=for-the-badge"></a>
  <a href="https://github.com/Lincoln-Madaraka/erpgo"><img alt="Source code on GitHub" src="https://img.shields.io/badge/Source_code-2a1f17?style=for-the-badge&logo=github&logoColor=white"></a>
</p>

**A whole business in one Laravel 12 app: accounting, stock, people, sales, projects and more, as 52 module packages.** Books that always balance, stock that cannot go below zero, and roles enforced on the server for every page, export and approval. Based on WorkDo's ERPGo and written independently, one module at a time.

<table>
  <tr>
    <td width="50%"><img src="assets/shot-erpgo-inventory.webp" alt="ERP Go inventory: a stock movement form above stock on hand by warehouse."><br><sub><b>Inventory</b>: receipts, issues and warehouse transfers that never go below zero</sub></td>
    <td width="50%"><img src="assets/shot-erpgo-people.webp" alt="ERP Go people and leave: employee records and a request for annual leave."><br><sub><b>People &amp; leave</b>: employee records, leave balances and manager review</sub></td>
  </tr>
  <tr>
    <td width="50%"><img src="assets/shot-erpgo-sales.webp" alt="ERP Go sales invoices with search, status filters and export."><br><sub><b>Sales</b>: invoices with search, status filters, CSV export and approvals</sub></td>
    <td width="50%"><img src="assets/shot-erpgo-crm.webp" alt="ERP Go CRM register with leads and opportunities."><br><sub><b>CRM</b>: leads, opportunities, pipelines and activities</sub></td>
  </tr>
</table>

<details>
  <summary><b>How it is built</b></summary>
  <br>

- **A package for every business area.** Each of the 52 areas is its own Composer package with a manifest. One module registry reads them all, so a new module never touches the core.
- **Books that always balance.** Money is stored as whole cents, a journal posts only when its debits equal its credits, posted entries are never edited, and the trial balance is added up live.
- **Stock that cannot go below zero.** Per-warehouse quantities are kept in thousandths of a unit. Receipts, issues and transfers each run in one transaction, and a movement that would leave a warehouse short is refused with the reason.
- **Roles that hold on the server.** Nine roles decide who can see, export and approve what. Nobody can approve their own request or their own leave.
- **Useful while it grows.** Modules without their own engine yet share one register with search, filters, CSV export, approvals and a full audit history.

**Stack:** PHP 8.2 · Laravel 12 · MySQL · JavaScript · Vite
</details>

<br>

### 03 &nbsp;/&nbsp; OptimaERP

<a href="https://madaraka.work/work/optimaerp">
  <img src="assets/showcase-optimaerp.webp" alt="OptimaERP: sales invoices in KSh, the staff list and an open sales invoice." width="100%">
</a>

<p align="center">
  <a href="https://madaraka.work/work/optimaerp"><img alt="Read the case study" src="https://img.shields.io/badge/Read_the_case_study-a9622b?style=for-the-badge"></a>
  <a href="https://github.com/Lincoln-Madaraka/OptimaERP"><img alt="Source code on GitHub" src="https://img.shields.io/badge/Source_code-2a1f17?style=for-the-badge&logo=github&logoColor=white"></a>
</p>

**ERPNext, the open-source ERP, renamed end to end and set up so a business can try it as each of its own staff.** A login for every job, from a read-only CEO to a cashier fenced to their own sales, with invoicing set up for the Kenyan market. ERPNext's GPL licence, credits and links are kept exactly where they were; only the name changed.

<table>
  <tr>
    <td width="50%"><img src="assets/shot-optimaerp-staff.webp" alt="OptimaERP staff list: nineteen demo employees with departments and job titles."><br><sub><b>Staff</b>: nineteen demo employees, each with their own department and job title</sub></td>
    <td width="50%"><img src="assets/shot-optimaerp-invoice.webp" alt="An OptimaERP sales invoice with customer, posting date, warehouse and line items in KSh."><br><sub><b>Sales invoice</b>: customer, posting date, stock warehouse and line items in KSh</sub></td>
  </tr>
</table>

<details>
  <summary><b>How it is built</b></summary>
  <br>

- **Renamed all the way through.** App, Python package, JavaScript namespace and asset paths, with Frappe HR rewired to depend on it. The rename runs from a script, so it is re-run rather than redone when ERPNext moves on.
- **A login for every job.** 22 demo logins built from role profiles, from a read-only CEO to a cashier fenced to their own sales. Customer, supplier and employee portals each see only their own records.
- **Nothing a demo user can break.** The CEO role can read, report and export on 28 document types and write on none. Delete rights came off sixteen records a demo depends on, so any login can be handed over mid-meeting.
- **Invoices that fit the local market.** KSh, a letter head on every document, 16% VAT on by default, M-Pesa as a payment method, and PDF printing through a bundled Chromium.

**Stack:** Frappe · Python · PostgreSQL · Redis · JavaScript
</details>

<br>

### 04 &nbsp;/&nbsp; madaraka.work

<a href="https://madaraka.work">
  <img src="assets/showcase-portfolio.webp" alt="madaraka.work on desktop and phone: the home page, the work index and the mobile layout." width="100%">
</a>

<p align="center">
  <a href="https://madaraka.work"><img alt="Visit madaraka.work" src="https://img.shields.io/badge/Visit_madaraka.work-a9622b?style=for-the-badge"></a>
</p>

**The full story behind everything on this page.** Every system gets a written case study with its architecture and screenshots, and most have a recorded walkthrough. I built the site in Next.js and React to learn that stack properly instead of reading about it.

<table>
  <tr>
    <td width="50%"><img src="assets/shot-portfolio-case.webp" alt="The BloodAfya case study on madaraka.work, with shared test logins and a link to the live app."><br><sub><b>Case studies</b>: the problem, the constraints, the approach, the architecture and the outcome</sub></td>
    <td width="50%"><img src="assets/shot-portfolio-services.webp" alt="The services page on madaraka.work: your whole business, in one system."><br><sub><b>Services</b>: what each engagement delivers, the signs it fits, and how long it takes</sub></td>
  </tr>
</table>

<details>
  <summary><b>How it is built</b></summary>
  <br>

- **Try before you trust.** BloodAfya's case study hands out live demo logins with a guided tour.
- **Search everything.** Site-wide search with a command palette.
- **Built to be looked at.** 3D and motion work with Three.js, React Three Fiber and GSAP, tuned to settle instantly for people who prefer reduced motion.

**Stack:** Next.js 15 · React 19 · TypeScript · Three.js · GSAP · Motion
</details>

<br>

**Also on [madaraka.work](https://madaraka.work/work):** RedGiant Heartbeat, the Laravel ERP an agency runs its projects, people, assets and field check-ins on; Radian, a client platform at [rideradian.com](https://www.rideradian.com); and TinkaCode, learning tools for a children's coding and robotics school.

<br>

## Stack

<table>
  <tr>
    <td width="150"><b>Core</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=php,laravel,mysql,js,html,css,linux,git,bash,wordpress&theme=dark">
        <img alt="PHP, Laravel, MySQL, JavaScript, HTML, CSS, Linux, Git, Bash, WordPress" src="https://skillicons.dev/icons?i=php,laravel,mysql,js,html,css,linux,git,bash,wordpress&theme=light">
      </picture>
    </td>
  </tr>
  <tr>
    <td width="150"><b>Shipped with recently</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=ts,react,nextjs,postgres,tailwind,redis,py,threejs,vercel,vitest&theme=dark">
        <img alt="TypeScript, React, Next.js, PostgreSQL, Tailwind CSS, Redis, Python, Three.js, Vercel, Vitest" src="https://skillicons.dev/icons?i=ts,react,nextjs,postgres,tailwind,redis,py,threejs,vercel,vitest&theme=light">
      </picture>
    </td>
  </tr>
  <tr>
    <td width="150"><b>Learning now</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=nodejs,mongodb&theme=dark">
        <img alt="Node.js, MongoDB" src="https://skillicons.dev/icons?i=nodejs,mongodb&theme=light">
      </picture>
    </td>
  </tr>
</table>

Also: REST APIs, SSH and server administration, hosting and system migrations, dashboards and data visualisation, the OpenAI API and workflow automation.

<br>

## Experience

| When | Role | Where |
| --- | --- | --- |
| 2025 – present | Developer Operations & Software Automation Engineer | Red Giant Media Agency, Nairobi |
| 2024 – present | Software Engineer, freelance | Upwork, remote |
| 2024 | DevOps Trainee | CMC Motors Group, Nairobi |
| 2023 – 2024 | Software Developer & IoT Instructor | TinkaCode Kenya |
| 2022 – 2023 | Web Developer & Instructor | Digital Opportunity Trust Kenya |

**BSc Telecommunications and Information Engineering**, Kenyatta University, 2020 – 2025. Second Class Honours, Upper Division.<br>
**Diploma, Full-Stack Software Engineering**, ALX Africa, 2024 – 2025. Back-end specialisation.

<details>
  <summary><b>Certificates (6)</b></summary>
  <br>
  <table>
    <tr>
      <td width="33%" align="center" valign="top"><a href="project-3.png"><img src="project-3.png" alt="ALX Software Engineering certificate of completion"></a><br><sub><b>ALX Software Engineering</b><br>12-month programme, back-end specialisation. 2025</sub></td>
      <td width="33%" align="center" valign="top"><a href="GCP_CERT.png"><img src="GCP_CERT.png" alt="Udemy certificate for the Google Cloud Professional Cloud Architect course"></a><br><sub><b>Google Cloud Professional Cloud Architect</b><br>Udemy course. 2025</sub></td>
      <td width="33%" align="center" valign="top"><a href="project-5.jpeg"><img src="project-5.jpeg" alt="Power Learn Project certificate of achievement"></a><br><sub><b>Power Learn Project</b><br>16-week software development programme, web specialisation. 2024</sub></td>
    </tr>
    <tr>
      <td width="33%" align="center" valign="top"><a href="project-11.png"><img src="project-11.png" alt="Google Technical Support Fundamentals certificate on Coursera"></a><br><sub><b>Technical Support Fundamentals</b><br>Google, via Coursera. 2024</sub></td>
      <td width="33%" align="center" valign="top"><a href="AI_FOR_CYB.png"><img src="AI_FOR_CYB.png" alt="LinkedIn Learning certificate for Artificial Intelligence for Cybersecurity"></a><br><sub><b>Artificial Intelligence for Cybersecurity</b><br>LinkedIn Learning. 2024</sub></td>
      <td width="33%" align="center" valign="top"><a href="Lincoln%20LinkedIn%20Certfied.png"><img src="Lincoln%20LinkedIn%20Certfied.png" alt="LinkedIn Learning certificate for Git Essential Training"></a><br><sub><b>Git Essential Training</b><br>LinkedIn Learning. 2024</sub></td>
    </tr>
  </table>
</details>

<br>

## Let's build something

<a href="https://madaraka.work/contact">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/cta-dark.webp">
    <img src="assets/cta-light.webp" alt="Have a system that needs building? Tell me which manual process hurts most, and I will tell you what I would build first. Start a conversation, or email softwares.lincoln@gmail.com. Open to new work." width="100%">
  </picture>
</a>

<p align="center">
  <a href="https://madaraka.work/contact"><img alt="Start a conversation" src="https://img.shields.io/badge/Start_a_conversation-a9622b?style=for-the-badge"></a>
  <a href="mailto:softwares.lincoln@gmail.com"><img alt="Email softwares.lincoln@gmail.com" src="https://img.shields.io/badge/Email_me-2a1f17?style=for-the-badge"></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Lincoln-Madaraka&label=Profile%20views&color=a9622b&style=flat-square" alt="Profile views">
  <a href="https://wakatime.com/@c1bac4c9-c60a-4d0f-bf5e-78ee4d291507"><img src="https://wakatime.com/badge/user/c1bac4c9-c60a-4d0f-bf5e-78ee4d291507.svg" alt="WakaTime"></a>
</p>

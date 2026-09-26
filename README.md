<!-- Header -->
![header](https://capsule-render.vercel.app/api?type=waving&height=300&color=timeGradient&section=header&reversal=true&text=Aris+Artates&textBg=false&fontSize=70&fontAlign=50&fontAlignY=50&animation=fadeIn&rotate=0&strokeWidth=0&desc=Software+Development+%E2%80%A2+Automation+%E2%80%A2+Game+Development&descSize=20&descAlign=50&descAlignY=60)

<div align="center">
  <img src="https://readme-typing-svg.demolab.com/?size=24&color=0D9488&pause=1200&center=true&vCenter=true&width=460&lines=Software+Developer;Business+Logic+%26+Data-Heavy+UIs;Tooling+%26+Automation;Keyboard+Firmware+Tinkerer;Aspiring+Game+Developer" alt="Software Developer · Business Logic & Data-Heavy UIs · Tooling & Automation · Keyboard Firmware Tinkerer · Aspiring Game Developer" />
  <br />
  <img src="https://komarev.com/ghpvc/?username=Aris-Artates&color=0D9488&style=flat-square&label=profile+views" alt="Profile views" />
</div>

<p align="center">
  I mostly build web applications, working across both the frontend and backend. A lot of what I work on involves things like payroll calculations, permissions, database-heavy features, and internal tools.
</p>

<p align="center">
  My usual stack is Next.js and TypeScript on the frontend, with Node.js, Python, and PostgreSQL on the backend. I also write smaller scripts and tools when they make testing, automation, or day-to-day development easier.
</p>

<p align="center">
  <a href="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExdnRhaWpjb3Y2b2ZrcDB3c3NkcXd6MXQxamhtOXZuZmVybjJiYTF3NyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9cw/TcWh1QKPlaWAyhrWmG/giphy.gif"><b>Portfolio</b></a> &nbsp;·&nbsp;
  <a href="https://github.com/Aris-Artates?tab=repositories"><b>All Repositories</b></a> &nbsp;·&nbsp;
  <a href="https://www.linkedin.com/in/aris-artates"><b>Connect</b></a>
</p>

---

<h3 align="center">What I Build</h3>

<table>
  <tr>
    <td width="33%" valign="top">
      <b>Business web platforms</b><br />
      <sub>Web apps with role-based access, business rules, calculations, approval workflows, audit logs, dashboards, and reporting.</sub>
    </td>
    <td width="33%" valign="top">
      <b>Developer &amp; data tooling</b><br />
      <sub>Tools for checking data, comparing environments, automating repetitive tasks, and catching problems before they reach users.</sub>
    </td>
    <td width="33%" valign="top">
      <b>Games &amp; hardware</b><br />
      <sub>Small games and hardware projects, including typing games, keyboard tools, raw HID communication, and custom firmware.</sub>
    </td>
  </tr>
</table>

---

<h3 align="center">Engineering Experience</h3>

<p align="center"><sub>Based on production team work and personal projects. Private work is described by what I worked on rather than by project name.</sub></p>

#### Domain logic &amp; data-heavy interfaces

- Built the **payroll calculation layer** for an HR and payroll platform, covering gross and taxable income, withholding tax, overtime, night differential, net pay, and centavo-level rounding. The calculations were later refactored to match the client's formulas exactly.

- Worked on the main **payroll summary table**, including per-column drill-downs, combined frequency and date filters, reusable footer totals, record locking, and negative net-pay warnings. Payslips use the same underlying data.

- Built an **approval-to-payment workflow** with verified totals, an approver queue, pending counts, role-specific dashboards, and access checks before payment.

- Worked on deduction, installment, and loan tracking, along with configurable print layouts for columns, margins, scaling, and templates. Some dashboards also defer chart loading until the charts are actually needed.

#### Access control, security &amp; auditability

- Extended a **deny-by-default role system** with view-only, staff, approving-officer, and superadmin roles. Write access is checked against an allow-list of read-only endpoints in both the API proxy and client.

- Built an **audit logging module** that records the user responsible for an action, removes passwords and tokens from logged payloads, and keeps logging failures from breaking the original write operation. I also wrote the backend hand-off specification for an append-only log table with hash chaining.

- Set up **single sign-on between two applications without sharing cookies**. One application issues an HMAC-SHA256 signed session cookie and the other verifies it locally, keeping the main session isolated from other subdomains.

- Rebuilt a static documentation site as an **Express + PostgreSQL** application with CSRF protection, Helmet, rate limiting, row-level security, and per-page and per-role editing permissions.

<details>
<summary><b>More: frontend architecture, backend &amp; integration</b></summary>

<br />

- **Data fetching:** Built shared SWR hooks for employee, payroll, reference-data, audit, and approval queries. I also added cache resets between user sessions and moved monitoring pages onto the shared hooks.

- **Reusable UI:** Built sticky-column tables with edge scrolling, shared frequency-of-application controls, an employee picker that removes duplicate names, and date-range overlap checks.

- **Backend-for-frontend:** Worked with a Next.js API proxy that maps route keys to a separate WordPress REST backend while adding endpoints and access checks.

- **Search:** Built a fuzzy search implementation using bounded edit distance, with queries taking around 0.5 ms against a static content index.

- **Content storage:** Designed a database-backed editing system where only changes from the original repository files are stored. If an edit is empty, the original file is used instead.

- **Maps at scale:** Worked with around 7,500 geotagged records on a Leaflet map using clustering, canvas rendering, and virtualized lists. The system also uses ISR, a protected revalidation endpoint, and data synchronization that only publishes after sanity checks.

</details>

#### Tooling, automation &amp; verification

- Wrote **verification scripts** for a codebase without a test runner. They check role coverage, audit classifications, payment gates, and installment rules to catch regressions in important business logic.

- Built a **CSV consistency checker** with a rule engine, generic and schema-specific rules, HTML reports with SVG charts, GUI and CLI modes, CI-friendly exit codes, 79 unit tests, and a single-file Windows executable.

- Built a **cross-environment diff tool** with Playwright that logs into multiple deployments of the same application, reads tables through their DataTables API, compares values against a baseline, and records load times.

- Wrote a Chrome extension content script for filling **React-controlled forms** from spreadsheet rows using native value setters and synthetic events.

#### Hardware &amp; low-level

- Built a **keyboard overlay** that reads the key matrix through the Vial raw HID protocol at around 60 Hz, gets the layout definition directly from the board, and falls back to OS keyboard hooks on Windows and Linux. Releases are built with PyInstaller through tagged GitHub Actions releases, with udev rules and a systemd user service on Linux.

- Moved my layout to a new Corne PCB using **custom Vial-QMK firmware** in C, including last-input-wins SOCD handling for the gaming layer.

#### How I work

- Worked for six months on a six-plus developer team using personal branches, ticket-numbered commits, and merge requests promoted through `dev`, `stg`, and `main`.

- Used issue-driven branching and reviewed pull requests on a public team project with 100+ merged PRs.

---

<h3 align="center">Game Development</h3>

<p align="center"><sub>Side projects focused on 2D game development, interaction design, and learning more about split keyboards.</sub></p>

| Project | Description | Stack | Status |
|---|---|---|---|
| Corne-troll Tower | Browser tower defense game built around learning the 46-key Corne keyboard with Programmer Dvorak | HTML5, JavaScript | Repo not public |
| [Actuation Point](https://github.com/Aris-Artates/ActuationPoint) | Infiltration-themed typing trainer for Corne and Dvorak | Python | Public |
| 2p2p | Two-player, two-perspective puzzle story game. Restarted from scratch in pygame-ce as a hands-on learning project | Python, pygame-ce | Early prototype |

---

<h3 align="center">Public Work</h3>

<p align="center"><sub>Public projects and prototypes that are available as references.</sub></p>

| Project | What It Is | Stack | Status |
|---|---|---|---|
| [Valarx](https://github.com/Aris-Artates/valarx) | Community website covering introductions, events, and team information, with a FastAPI backend being developed | Next.js, TypeScript, Tailwind, FastAPI | [Live](https://valarx.vercel.app) |
| [Tax System](https://github.com/Aris-Artates/tax-system) | Property tax administration system developed by a team using issue-driven development and reviewed pull requests | Next.js, TypeScript, Supabase | Team project |
| [ExamPrep](https://github.com/Aris-Artates/examprep) | Exam platform with local live streaming using FFmpeg and Nginx RTMP, plus an XGBoost and LightGBM score predictor | Next.js, FastAPI, Supabase | Prototype |
| [LiveFB](https://github.com/Aris-Artates/livefb) | Learning platform with Facebook Live integration, local-LLM recommendations, and live Q&amp;A | Next.js, FastAPI, Ollama, Supabase | Prototype |
| [AITutor](https://github.com/Aris-Artates/aitutor) | Web-based AI tutoring platform using the Claude API | Next.js, TypeScript, Supabase | Prototype |

---

<h3 align="center">Tech Stack</h3>

<p align="center"><sub>Technologies I've actually built or shipped something with.</sub></p>

<table align="center">
  <tr>
    <td align="right"><b>Languages</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=ts,js,python,c,html,css&theme=dark" />
        <img src="https://skillicons.dev/icons?i=ts,js,python,c,html,css&theme=light" height="40" alt="TypeScript, JavaScript, Python, C, HTML, CSS" />
      </picture>
    </td>
  </tr>
  <tr>
    <td align="right"><b>Frontend</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=nextjs,react,tailwind&theme=dark" />
        <img src="https://skillicons.dev/icons?i=nextjs,react,tailwind&theme=light" height="40" alt="Next.js, React, Tailwind CSS" />
      </picture>
      <br /><sub>SWR · Radix UI / shadcn · Recharts · Leaflet · Alpine.js</sub>
    </td>
  </tr>
  <tr>
    <td align="right"><b>Backend &amp; Data</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=nodejs,express,fastapi,supabase,postgres&theme=dark" />
        <img src="https://skillicons.dev/icons?i=nodejs,express,fastapi,supabase,postgres&theme=light" height="40" alt="Node.js, Express, FastAPI, Supabase, PostgreSQL" />
      </picture>
      <br /><sub>REST APIs · row-level security · JWT / signed-cookie auth · WordPress REST as a consumer</sub>
    </td>
  </tr>
  <tr>
    <td align="right"><b>Infra &amp; Tooling</b></td>
    <td>
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://skillicons.dev/icons?i=git,github,gitlab,githubactions,vercel,nginx,linux&theme=dark" />
        <img src="https://skillicons.dev/icons?i=git,github,gitlab,githubactions,vercel,nginx,linux&theme=light" height="40" alt="Git, GitHub, GitLab, GitHub Actions, Vercel, Nginx, Linux" />
      </picture>
      <br /><sub>Playwright · PyInstaller · systemd / udev · Postman</sub>
    </td>
  </tr>
  <tr>
    <td align="right"><b>Games &amp; Hardware</b></td>
    <td><sub>pygame-ce · QMK / Vial firmware · raw HID · HTML5 Canvas</sub></td>
  </tr>
</table>

<details>
<summary><b>Also used before, lighter experience</b></summary>

<br />

PHP · Lua · .NET · jQuery · WordPress · Docker · Railway · Selenium · Ollama · XGBoost / LightGBM · FFmpeg

</details>

**Currently exploring:** game development with pygame-ce, keyboard firmware, and running LLMs locally.

---

<h3 align="center">Developer Metrics</h3>

<p align="center"><sub>Most of my day-to-day work is in private team repositories, so these stats only show part of what I work on. I mainly keep them around to track how they're changing over time.</sub></p>

<p align="center">
  <img src="https://github-stats-extended.vercel.app/api?username=Aris-Artates&show_icons=true&hide_border=true&bg_color=00000000&title_color=0D9488&icon_color=0D9488&text_color=888888&rank_icon=github&hide=issues" height="160" alt="GitHub stats" />
  <img src="https://github-stats-extended.vercel.app/api/top-langs/?username=Aris-Artates&layout=compact&hide_border=true&bg_color=00000000&title_color=0D9488&text_color=888888" height="160" alt="Top languages" />
</p>

---

<h3 align="center" id="connect">Connect</h3>

<p align="center">
  <a href="https://portfolio-aris-artates-projects.vercel.app">
    <img src="https://img.shields.io/badge/Portfolio-0D9488?style=for-the-badge&logo=vercel&logoColor=white" alt="Portfolio" />
  </a>
  <a href="https://github.com/Aris-Artates">
    <img src="https://img.shields.io/badge/GitHub-0D9488?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" />
  </a>
  <!-- Add more links here (e.g. LinkedIn, email) using the same badge style. -->
</p>

<p align="center">
  <i>Open to collaborations on business web platforms, system integration, developer tooling, and civic tech.</i>
</p>

![footer](https://capsule-render.vercel.app/api?type=waving&color=timeGradient&reversal=true&height=120&section=footer&desc=last%20updated%202026-09-24&descSize=14&descAlignY=80)

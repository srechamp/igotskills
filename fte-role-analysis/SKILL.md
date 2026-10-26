---
name: "fte-role-analysis"
description: "Evaluate and prep one to five full-time job applications at once (links, PDFs, docx, or pasted JDs): hiring-manager go/no-go, layoff check, gap analysis, ranking from most to least qualified, ATS-tailored resume, recruiter screen prep, interview questions, 1-week ramp-up project with business value, 30/60/90-day plan, JD status check, and a results doc. Use whenever Devin shares one or more direct-hire postings, asks which of several roles to apply to, or wants roles compared."
---

# Full-Time Role Analysis

Use when Devin shares one or more full-time (direct-hire) job postings, in any mix of URLs, PDFs, docx files, or pasted text, or invokes this skill by name. For roles submitted through a staffing agency, use `contract-role-analysis` instead.

The steps run in order. Steps 1 and 2 are gates: they exist so no time is spent tailoring a resume for a role that isn't worth applying to.

## Single vs. batch runs

The skill handles **up to 5 roles per run.**

- **One role:** run Steps 0–8, then the Wrap-up, as written.
- **Two to five roles (batch):** the full prep (tailored resume, project, 30/60/90 plan) is a lot of work per role, so a batch runs in two phases. That way the effort goes to the roles worth it.
  1. **Screen every role:** run Steps 0–3 and the JD status refresh (see Wrap-up) for each role. Keep each role's results separate and labeled `Role 1 — {Company}, {Title}` and so on.
  2. **Rank** the roles (see "Batch ranking" below).
  3. **Ask which roles get the full prep** (Steps 4–8). Recommend the top PASS roles that are still live. If Devin says "all", run every role that didn't FAIL. If Devin isn't there to answer, run the full prep on the #1 ranked role only, and say so.
  4. Finish with the Wrap-up, including the results doc.
- **More than 5 roles:** say the limit is 5 per run and ask which 5 to start with. If Devin isn't there to answer, take the first 5 in the order he gave them and list the rest for a second run.

Batch gate behavior: a FAIL or a High layoff risk does not stop the batch. For a FAIL, record the verdict, skip the rest of that role's steps, and continue with the others. A High-risk role still gets its Step 3 gap analysis so it can be ranked. In the ranking, note which roles were stopped or flagged and why.

## Step 0 — Intake

1. Collect every job description:
   - **URLs:** fetch each one with WebFetch. If a page is behind a login wall (LinkedIn, often), say which one and ask Devin to paste the text or attach a PDF. Continue with the others in the meantime.
   - **PDF / docx:** read each attachment.
   - **Pasted text:** if several JDs are pasted in one message, split them at clear boundaries (a new company name or title, a separator, a new "About the role"). If the split is ambiguous, state how many roles you found and what you took each to be before continuing.
   - If no JD was provided, ask for one and stop.
2. Before any analysis, run these checks on the set:
   - **Duplicates:** the same requisition posted on two boards counts as one role. Keep the company's own careers page or ATS link as the primary.
   - **Contract / agency roles:** if one comes through a staffing agency or vendor, take it out of the batch and offer to run `contract-role-analysis` on it.
   - **Same company twice:** do the Step 2 layoff research and the Step 7 business research once, then reuse it for both roles.
3. Record for each role: company, exact role title, location/remote policy, level, salary range if listed, the posting date if visible, the JD URL, and any requisition / job ID.
4. Keep a copy of the key JD fields for each role (title, level, salary range, location policy, top requirements). The wrap-up compares against these to detect changes.
5. Check `applications/` in project knowledge for an earlier analysis of the same role. If there is one, say so and focus on what changed rather than starting from zero.
6. Load the source resume: `Devin_Bess_Resume.docx` from project knowledge (or a newer version if Devin attached one in this conversation — the attached one wins). This is the only source of truth for Devin's experience, and every role in a batch is screened against the same version.
7. Anchor all date-relative work to today's date from the conversation.

## Step 1 — Hiring-manager screen (GATE)

Act as the hiring manager for this specific role, reading the resume as it stands today (untailored). Be candid; a flattering score wastes Devin's time.

Produce:
- **Verdict:** PASS / BORDERLINE / FAIL, plus a 0–100 fit score.
- **Required qualifications table:** requirement | evidence on resume | Met / Partial / Missing.
- **Nice-to-haves:** same format, briefly.
- **Knockout factors:** years of experience, clearance, location, degree, domain, level mismatch (over- or under-leveled).
- **Why:** 3–5 sentences on what would make a hiring manager advance or reject this resume.

Gate rule:
- **FAIL** → stop here. Report the verdict and reasons, and ask whether Devin still wants the remaining steps. (In a batch, stop only this role; see "Batch gate behavior".)
- **BORDERLINE** → continue, but carry the specific weak points forward into Steps 4–8.
- **PASS** → continue.

## Step 2 — Layoff and stability check (GATE)

Search the web; do not answer from memory. Window: the last 12 months from today.

Look for: layoffs / RIFs (especially Engineering, IT, Infrastructure, Operations), hiring freezes, reorganizations, acquisitions, WARN Act notices, and executive turnover in the org this role sits in. Useful sources: layoffs.fyi, state WARN notice databases, major news outlets, company press releases and earnings calls. Treat forums (e.g., TheLayoff, Blind) as low-confidence signal only and label them as such.

Report each finding with date, scope, departments affected, and a source link. If nothing turns up, say so and list what was searched. End with a one-line risk read: Low / Moderate / High, and whether this role could plausibly be a backfill for cut headcount.

If risk is High, pause and ask before continuing. (In a batch, flag it and keep screening the other roles; ask about this one when you present the ranking.)

## Step 3 — Skills match and gap analysis

From the JD's responsibilities, requirements, and nice-to-haves, build:

| JD item | Resume evidence | Status (Strong / Partial / Gap) | Notes |

Then sort the gaps into:
- **Closable in a week** — feeds Step 7.
- **Adjacent** — Devin has related experience he can speak to credibly (name the resume line).
- **Real gap** — can't be closed quickly; decide how to address it honestly in interviews. Feeds the gap-closing plan in Step 8.

## Batch ranking (batch runs only, after Step 3 and the JD status refresh)

Rank the roles from **most qualified to least qualified.** "Qualified" means how well Devin's resume, as it stands today, matches what the role asks for. It does not mean how attractive the role is.

Order by:
1. **Fit score** from Step 1 (higher first).
2. **Ties** (within 3 points): fewer Missing required qualifications first, then fewer Step 3 real gaps.

Layoff risk, JD status and comp do not change the order. They go in their own columns so Devin can weigh them himself, and a role that is closed or stopped still keeps its place with a clear flag.

Present the ranking as a table:

| Rank | Company — Role | Verdict | Fit score | Required quals met | Real gaps | Layoff risk | JD status | Comp (posted) | Recommended action |
|---|---|---|---|---|---|---|---|---|---|

Under the table, write one or two sentences per role on why it sits where it does, naming the deciding requirement or gap. Then add a short **"Where to focus"** note. If the most qualified role isn't the best bet (closed posting, High layoff risk, comp well below the others, a knockout factor), say so plainly and name the role you would prep first.

## Step 4 — Tailor the resume

### Integrity rules (non-negotiable)
- **Never add** a skill, tool, language, certification, employer, title, date, or metric that is not already in the source resume.
- Allowed: reorder bullets and sections, rewrite vague bullets for clarity and impact, adopt the JD's exact phrasing for skills Devin genuinely has (e.g., JD says "Amazon EKS" and resume says "Kubernetes (EKS)"), adjust the summary and headline to the role, trim or drop bullets irrelevant to this role.
- If a bullet would be much stronger with a number that isn't on the resume, **ask Devin** for it. Never estimate or invent one.

### ATS formatting rules
- Single column. No tables, text boxes, columns, headers/footers holding content, images, or icons.
- Standard section headings: Professional Summary, Skills, Professional Experience, Certifications, Education.
- Contact info in the document body, not in a header.
- Consistent date format (Month YYYY – Month YYYY). Job title, company, location, dates on predictable lines.
- Standard fonts, no special bullet glyphs beyond simple round bullets.
- Keywords from the JD appear in context within bullets, not only in the skills list.
- Keep it to two pages.

### Output
- Read the `docx` skill before building. Build a .docx named `Devin_Bess_Resume_{Company}_{Role}.docx`.
- Include a **change log** in the reply: each modified bullet as before → after, with the JD requirement it targets. List any bullets removed and why.
- List any questions for Devin (missing metrics, clarifications) separately.

## Step 5 — Recruiter screen prep

The recruiter screen is a 15–30 minute filter on logistics, compensation, motivation, and basic fit, not a technical interview. Prep Devin to pass it cleanly and to leave with the information he needs.

### A. Questions the recruiter is likely to ask
For each, give a short suggested answer grounded in the resume and Devin's stated targets (senior SRE / Platform / DevOps, hybrid or fully remote, based in Durham, NC). Never invent facts; where an answer depends on something only Devin knows, mark it **[Devin to fill]**.
- "Walk me through your background" — a 60–90 second pitch tailored to this JD, ending on why this role.
- "Why are you looking / why are you leaving?" — honest, forward-looking framing.
- "Why this company?" — one or two specifics from the company research (product, mission, Step 7 business value), not generic praise.
- "What are your salary expectations?" — research the market before answering: the posted range, state pay-transparency postings, levels.fyi, Glassdoor, and comparable postings, with sources. Give a recommended range and a script that anchors on total compensation and the posted range where possible. Do not assume Devin's current pay.
- Location, remote/hybrid, and relocation fit against the JD's policy.
- Availability / notice period and start date — **[Devin to fill]**.
- Work authorization and sponsorship — **[Devin to fill]** if not already known.
- "Where else are you interviewing?" — a safe way to signal an active search without naming companies.
- Any knockout factor from Step 1 (years, level, domain, degree) — how to address it in one or two sentences before the recruiter screens him out.

### B. Questions for Devin to ask the recruiter
Pick 8–12, tailored to this role and anything Steps 1–3 turned up:
- **Why the role is open:** new headcount or backfill? How long has it been open? (Tie to Step 2 — if there were layoffs, ask directly whether this backfills a cut position.)
- **Team and reporting:** team size, who the role reports to, how the SRE/Platform team fits in the engineering org.
- **Level and title:** what level is this mapped to internally, and how is leveling decided?
- **Compensation structure:** confirmed base range, bonus, equity (type, vesting), 401(k) match, and benefits — and whether the range is negotiable by level.
- **Work model:** remote/hybrid expectations, in-office days, travel, time-zone coverage.
- **On-call:** rotation size, frequency, compensation for on-call, typical page volume.
- **Interview process:** stages, format of each (live coding, system design, take-home), interviewers, and expected timeline to offer.
- **Success:** what the hiring manager most needs this person to fix or deliver in the first six months.
- **Process signal:** where they are in the search and how many candidates are in later stages.
- Anything ambiguous in the JD (stack, scope, level) that would change the go/no-go.

### C. Listen for
List the 3–5 answers that would be red flags for this specific role (e.g., backfill after a layoff, unrealistic scope for the level, on-call with no compensation, range far below the market range found above), and what Devin should do if he hears one.

## Step 6 — Interview questions

Base every question on the JD, grouped by the JD's own themes. Aim for 15–25 technical questions, including:
- Core stack questions for the tools named in the JD.
- At least one system design question sized to the role's level.
- At least one live troubleshooting / incident scenario ("production is down, walk me through it").
- SRE fundamentals where relevant: SLOs/SLIs/error budgets, on-call, postmortems, capacity, toil.
- Nice-to-have areas, marked as such.

For each question: what the interviewer is probing, and the key points of a strong answer, **tied to a specific real experience on Devin's resume** where one exists. Flag questions that hit a Step 3 gap.

Add 5–7 behavioral questions with the resume story that best answers each (STAR outline), and 5 sharp questions Devin can ask the interviewers (team health, on-call load, reliability maturity — and anything Step 2 turned up).

## Step 7 — One-week ramp-up project

### A. Business value research (do this first)
Search the web; do not answer from memory. The project should solve a problem the business actually has, so start by understanding the company's product and how well it performs today:
- **Product and customers:** what the company sells, who uses it, how it makes money, and which product area this role supports.
- **Service performance signals:** the public status page and its incident history (frequency, duration, affected components over the last 6–12 months), notable outages in the news, Downdetector or similar reports, and reliability or performance complaints in customer reviews (G2, Capterra, Trustpilot, app store reviews).
- **Business context:** recent earnings, funding, growth, SLAs or uptime commitments, compliance requirements (SOC 2, HIPAA, PCI, FedRAMP), cloud cost pressure, and stated engineering priorities (engineering blog posts, conference talks, the JD itself).

Report each signal with date and a source link, and label low-confidence sources. Do not invent numbers; if a dollar or customer impact can only be estimated, show the assumption and label it as an estimate.

Then write a **business value statement** (3–5 sentences): the specific problem, who it hurts (customers, revenue, engineers, compliance), and how the project addresses it, framed in business terms such as revenue protected, customer trust and churn, SLA exposure, MTTR, cost avoided, or developer velocity.

### B. Design the project
Extract the tech stack, tools, and any team projects or product areas named in the JD. Design a 5-day project (optional weekend polish) that:
1. Targets the business problem identified in 7A, modeled on the company's real product and failure modes (e.g., a simulated service that mirrors their recurring incident type).
2. Closes the "closable in a week" gaps from Step 3.
3. Demonstrates role readiness using the JD's actual stack.
4. Produces talking points for the Step 6 questions.

For each day: goal, tasks, and a concrete deliverable. The project should end in something showable: a public GitHub repo with a README that opens with the business problem and value statement, an architecture diagram, and a short write-up of decisions and trade-offs.

Guardrails: stay within free tiers or state expected cost; include a teardown step for any cloud resources; don't recreate anything proprietary to the employer; use only public information about their incidents.

### C. Output
Close with a table mapping project components → JD requirements → business value → interview questions they help answer. Add a 30-second pitch Devin can use in interviews or outreach: "I noticed X in your public incident history; here's how I'd approach it, and here's a working example."

## Step 8 — 30/60/90-day ramp-up plan

Step 7 gets Devin ready to interview. This step shows how he would ramp once hired. It doubles as interview material for "what would you do in your first 90 days?" and as a script for the hiring manager conversation. Build it from the JD, the Step 3 gaps, the Step 7 business value research, and anything Step 2 turned up. Do not write a generic onboarding checklist.

### Principles
- **Listen before changing.** Days 1–30 are for learning the system, the people, and the on-call reality. No big redesigns before Devin has seen a few real incidents and read the postmortems.
- **Earn trust with small, visible wins early,** then take on larger ownership by day 90.
- **Every item is concrete:** an owner or stakeholder, a deliverable, and how success is measured. Use the JD's own KPIs and language where they exist (MTTR, availability, SLOs, deploy frequency, toil).
- **Be honest about gaps.** Schedule time to close the Step 3 real gaps on the job (for example, the unfamiliar cloud, framework, or domain), and say so plainly rather than implying day-one expertise.
- **Use only what is real.** Tie phases to resume experience Devin actually has. Do not present metrics, tools, or results that are not on the resume as things he has already done. Targets for the new role are goals, not claims.
- **Size it to the role.** A growth-stage startup and a large enterprise need different plans. Adjust cadence and scope to the company's size and maturity.

### Structure
Produce three phases, each with a theme, objectives, key activities, and a deliverable or checkpoint:

| Phase | Theme | Typical contents |
|---|---|---|
| **Days 1–30** | Learn and listen | Environment access and tooling set up; read architecture docs, runbooks, SLO definitions, and the last 6–12 months of postmortems; shadow on-call, then join the rotation (secondary first if the company allows); 1:1s with the manager, the immediate team, and key partner teams (security, IT, product, support); map the service and dependency landscape; pick up 1–2 small, low-risk fixes or toil items; close the first Step 3 gap on the job (e.g., cloud-specific tooling). |
| **Days 31–60** | Contribute and own | Take primary on-call; own a defined slice of the platform (a service, pipeline, or alerting area); ship a first meaningful improvement tied to a JD priority (alert noise reduction, SLO or dashboard coverage, a Terraform module, a deploy safety check); write or improve runbooks and at least one postmortem; propose a prioritized reliability backlog based on what was learned. |
| **Days 61–90** | Lead and scale | Deliver a larger initiative that lines up with the JD's stated mission and the Step 7 business problem (e.g., PagerDuty migration, SLO and burn-rate alerting, IaC expansion, DR test, AI-assisted triage); present findings and a 6-month roadmap to the manager and stakeholders; define how success will be measured (targets for the JD's KPIs); document and hand off so the work does not live only in Devin's head. |

Customize every row for the actual role. Name the specific systems, tools, teams, and initiatives from the JD.

### Required elements
1. **Goals by day 30 / 60 / 90** — three to four outcomes per phase, each measurable or verifiable.
2. **Relationships and stakeholders** — who to meet, in what order, and what to ask each.
3. **Gap-closing plan** — which Step 3 gaps get addressed in which phase and how (pairing, docs, a sandbox project, a certification only if one is already on the resume or Devin chooses to pursue it).
4. **Risks and open questions to confirm before accepting** — pulled from Step 2 (stability, funding, leadership changes, on-call load), plus anything unclear in the JD or the recruiter screen. Phrase these so they can be asked in the final interview or offer stage.
5. **Success metrics** — how the manager would judge Devin at 30, 60, and 90 days, using the JD's own KPIs where available. Mark targets as proposed, to be agreed with the manager.
6. **Link to Step 7** — note which one-week project artifacts (repo, runbooks, dashboards) carry forward as day-one material or conversation starters.

### Output
- Keep the plan to roughly one page of content in the analysis (a table plus short bullets). If Devin asks, offer it as a standalone one-pager he can bring to a final-round interview.
- Close with 3 sentences Devin can say aloud when asked "what would your first 90 days look like?"

## Wrap-up

### JD status refresh
Before the summary, check whether the posting is still live. Postings close, get paused, or change while the analysis runs, and applying to a dead link wastes the work.
1. Re-fetch the JD URL with WebFetch.
2. Also check the company's own careers page or ATS (Greenhouse, Lever, Ashby, Workday, iCIMS) for the same title or requisition ID; a LinkedIn or job-board listing can outlive or predate the real one.
3. Report one status, with the check date and the URLs checked:
   - **Live — unchanged**
   - **Live — changed:** list what changed against the Step 0 copy (title, level, salary range, location policy, requirements) and whether it affects the verdict or the tailored resume.
   - **Taken down / closed:** 404, "no longer accepting applications," or missing from the careers page. Note it may be filled, paused, or reposted, and search for a reposted version under a similar title.
   - **Unable to verify:** login wall or blocked page. Say so; don't guess.
4. If it's down, change the recommended next step: reach out to the recruiter or hiring manager directly (offer the `coffee-chat` skill), watch for a repost, or skip.

In a batch, run this check for every role before ranking, and then once more right before the summary for any role that got the full prep.

### Summary
- **Single role:** end with a short summary: JD status, verdict, layoff risk, top 3 gaps, the one-line business value of the project, a one-line headline of the 30/60/90 plan, deliverables produced, and a recommended next step (apply now / apply after the project / reach out directly / skip).
- **Batch:** repeat the final ranking table (updated if a JD status changed), then give the same summary for each role that got the full prep, in rank order. Roles that were only screened get a single line each.

### Results doc
Always finish by asking Devin whether to create a doc recording the results. Ask it as a question with clear choices, for example:
- **Yes, create the doc** (recommended)
- **Yes, and also save each role to the project**
- **Not now**

If Devin isn't there to answer, create the doc anyway and say so.

When creating it, make it a doc: use the Docs artifact type or the `docs` skill when the session offers one, and fall back to a Markdown file otherwise. Title it `Role Analysis — {date}` for a batch, or `{Company} — {Role} Analysis` for a single role. Structure:
1. **Overview:** the run date, the resume version used, and the roles analyzed (with JD links).
2. **Ranking table** (batch only), with the "Where to focus" note.
3. **One section per role, in rank order:**
   - JD details: company, title, level, location policy, posted comp, posting date, link, status and check date.
   - Verdict, fit score and the required-qualifications table.
   - Layoff and stability findings, with sources.
   - Gap analysis summary: Strong / Adjacent / Real gaps.
   - For fully prepped roles: the resume file name and change-log highlights, recruiter screen prep, key interview questions, the project summary with its business value, and the 30/60/90 headline.
   - Recommended next step and any open questions for Devin.
4. **Sources:** all links cited, grouped by role.

Keep the doc factual and scannable. It is a record Devin will return to when a recruiter calls back, so lead each section with the verdict and the next step.

If Devin also wants the project copies, save each role to the project as `applications/{company}-{role}/analysis.md`, following the existing naming in that folder. If a file for that role already exists, update it instead of creating a duplicate.
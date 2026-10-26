---
name: "contract-role-analysis"
description: "Vet and prep a contract role submitted via a staffing agency: legitimacy check on each layer, requirements match, resume alignment, interview questions, 2–3 day ramp-up."
---

# Contract Role Analysis

Use when Devin is being submitted to a contract role through a staffing agency, vendor, or third party, or invokes this skill by name. For direct-hire roles, use `fte-role-analysis` instead.

Step 1 is a gate: if the chain doesn't check out, nothing else happens.

## Step 0 — Intake

1. Get the role description (URL, PDF, pasted text, or recruiter email). If missing, ask and stop.
2. Map the **submission pipeline**. Contract roles often pass through several layers, and each one must be verified separately. Example:
   - Staffing agency: Norwin Technologies
   - Third party / liaison / prime vendor: World Wide Technologies (WWT)
   - End client: Bearings
   If any layer is unknown, note it as a gap — an undisclosed end client is common early on but must be confirmed before Devin signs anything.
3. Record what's known about terms: rate, W-2 vs 1099 vs C2C, duration, extension or conversion potential, remote/onsite, clearance, start date.
4. Load the source resume: `Devin_Bess_Resume.docx` from project knowledge, or a newer version attached in this conversation (the attached one wins).
5. Anchor all date-relative work to today's date from the conversation.

## Step 1 — Legitimacy and scam check (GATE)

Search the web for each layer; do not answer from memory.

For the agency and any liaison, check:
- Business registration (state Secretary of State lookup), physical address, and how long the company has existed.
- Website quality and domain age; recruiter email domain matches the company domain (not Gmail/Outlook).
- The recruiter is a real person at that company on LinkedIn, with a plausible history.
- Glassdoor / Indeed / Google reviews, especially from contractors about pay reliability.
- Reports of this company name being used in recruiting scams (impersonation is common — a real company can be spoofed).

For the end client: confirm it exists and plausibly uses this kind of role and this vendor chain.

Red flags to call out explicitly:
- Requests for SSN, bank details, ID scans, or DOB before an offer and a real interview.
- Any payment asked of Devin (training, equipment, background check).
- Interviews only by chat (Telegram, WhatsApp, Signal) or with no video.
- Offer without an interview; rate far above market; vague role duties.
- Pressure to sign a right-to-represent or exclusivity agreement immediately.
- Check-cashing or equipment-reimbursement schemes.

Verdict per layer and overall: **Legitimate / Proceed with caution / Likely scam**, with source links.
- **Likely scam** → stop. Explain why and what Devin should not share.
- **Proceed with caution** → list exactly what to verify with the recruiter before going further.

Also give a short list of questions to ask the recruiter: end client confirmation, rate and pay structure, who Devin's employer of record is, pay frequency, benefits (if W-2), duration, extension/conversion odds, and right-to-represent terms (so Devin doesn't get double-submitted by two agencies).

## Step 2 — Role review and skills match

Extract the requirements section (required and preferred). Build:

| Requirement | Resume evidence | Status (Strong / Partial / Gap) | Notes |

Give a one-line **submission read**: strong match / competitive / stretch — contract screens are fast and literal, so be blunt about any required item with no resume evidence.

Sort gaps into: closable in 2–3 days (feeds Step 5), adjacent (can speak to it credibly), and real gap.

## Step 3 — Resume alignment (only if it helps)

Agencies often reformat or keyword-scan resumes themselves, so only tailor when it materially improves the match. If the current resume already covers the requirements well, say so and skip.

When tailoring:
- **Never add** a skill, tool, certification, employer, title, date, or metric not already on the source resume. Reword, reorder, trim, and adopt the requirement's exact phrasing only for skills Devin genuinely has. Ask Devin for any missing metric rather than inventing one.
- ATS-safe formatting: single column, no tables/text boxes/columns/images, standard section headings, contact info in the body, consistent dates, two pages max.
- Read the `docx` skill, then build `Devin_Bess_Resume_{Agency}_{Client-or-Role}.docx`.
- Give a change log: before → after for each edited bullet, with the requirement it targets.

## Step 4 — Interview questions

Contract interviews are often a short recruiter screen followed by one or two technical rounds with the client. Prepare:
- **Recruiter screen:** 3–5 likely questions (availability, rate expectations, why contract, quick stack confirmation) with suggested answers.
- **Technical:** 12–20 questions drawn from the requirements, including at least one hands-on troubleshooting scenario and one design/architecture question at the role's level. For each: what's being probed and key points of a strong answer, tied to a real experience on Devin's resume. Flag questions that hit a gap.
- **Behavioral:** 5 questions with STAR outlines from resume stories, weighted toward ramping up fast, working with client teams, and handling ambiguity — the things contract managers screen for.

## Step 5 — 2–3 day ramp-up project

Extract the stack and tools from the role. Design a 2–3 day hands-on build that touches as much of the required stack as possible and targets the closable gaps from Step 2.

For each day: goal, tasks, deliverable. End with something demonstrable (repo + README + diagram) and a short list of talking points that link the build to likely interview questions.

Guardrails: free tiers or stated cost, teardown steps for cloud resources, nothing proprietary to the client.

## Wrap-up

Summarize: legitimacy verdict, submission read, top gaps, deliverables produced, open questions for the recruiter, and recommended next step. Offer to save the analysis to the project as `applications/{agency}-{client}-{role}/analysis.md`.
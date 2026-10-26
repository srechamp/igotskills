---
name: coffee-chat
description: Draft an organic, human-sounding email or LinkedIn message to engineering leadership (engineering managers, platform/infra directors, VPs of Engineering, CTOs) asking for a 15-minute virtual coffee chat, then follow up with a nudge and thank-you. Use whenever the user wants to network, get a referral, do informational outreach, "reach out to" or "message" a manager/director/VP, send a cold DM, ask for a coffee chat, or stop cold-applying and start warm-channel job searching. Trigger even if they never say "coffee chat" (e.g., "what do I say to the director of platform at X", "write a LinkedIn note to this hiring manager", "I've applied to hundreds of jobs and nothing is working"). Not for replies to recruiters or staffing agencies (use contract-role-analysis) or for cover letters.
---

# Coffee Chat

Generate a short, genuine outreach message to a leader at a target company, asking for a 15-minute conversation about their platform challenges rather than a job.

**Why this skill exists:** In the current market, cold applications are mostly sifted by AI screening on one side and flooded by AI-optimized resumes on the other. Engineers on the market report that interviews mostly come from people they know, and referrals fill a disproportionate share of hires relative to how few applicants they are (see `references/market-signals-2026.md`). A warm message to a leader gets a human to read about the person before any filter does. That only works if the message sounds like a real person wrote it, so organic tone is the whole game.

## The user

Default assumption is candidate: Senior SRE / Platform / DevOps engineer, [N]+ years, [City, State], targeting senior SRE, Platform, and DevOps roles (full-time and contract), hybrid or remote. The resume is `candidate_resume.docx` in the project knowledge (use a newer one if attached to the chat). If the user is someone else, ask for their background in one line.

**Hard rule for anything drawn from the resume:** only mention skills, tools, employers, titles, dates, and metrics that are already on the resume. Reword freely, never invent. If a stronger line needs a number you don't have, ask. This matters because a leader may ask about any claim in the first call.

---

## Section 1: Networking and Referral (the core workflow)

### Step 1: Gather what makes the message real

A message is only organic if it contains something specific that only this sender, writing to this person, could say. Check what you have, and if any of the first three below are missing, **ask before drafting** (short, conversational, no more than 4 questions at once):

1. **Who and where:** name, title, company. (If they gave a LinkedIn URL or name, use it, but never invent biographical detail.)
2. **The genuine hook:** what about this person's team, platform, talk, post, or engineering blog is actually interesting to the user? If the user has no hook, offer to look one up with web search (recent engineering blog, conference talk, tech stack in job posts, funding or reorg news) and show sources. Anything about a company's current state must come from a search with sources, not memory.
3. **The connection (if any):** shared alma mater (NC A&T), former company, mutual contact, community, same tooling. Only claim a connection the user confirms.
4. **The credibility line:** which one piece of the user's experience is most relevant to this person's world? Propose one or two from the resume and let the user pick.
5. **Channel and tone:** LinkedIn connection note, LinkedIn DM/InMail, or email; formal or casual.

If the user gave enough up front, skip the questions and draft immediately, using `[bracketed placeholders]` for anything unknown. Then end with the prompts in Step 3.

### Step 2: Draft the message

Write two variants that differ in approach, not just wording (for example: "curiosity about their platform" vs. "shared background"), unless the user asked for one. Pick length by channel:

| Channel | Target length |
|---|---|
| LinkedIn connection note | under 300 characters |
| LinkedIn DM / InMail | 50-90 words |
| Email | 90-130 words, with 2-3 subject line options |

**What makes it feel human (and why):**
- Open with the specific hook, not with who you are. Leaders skim; a first line that proves you looked at their work earns the second line.
- Ask for their perspective on one concrete problem ("how are you handling X as the platform scales?"). People like answering questions about their own work; they dislike being auditioned.
- One credibility line, in plain words, tied to their world. Not a resume summary.
- One ask: 15 minutes, virtual, with a light out ("no worries if it's not a good week").
- Do not ask for a job, do not attach a resume, do not mention a specific opening. If the conversation goes well, the referral conversation happens live.
- Be honest about the situation without making it the headline. Don't pretend to be employed or "just curious" if the person might reasonably guess otherwise; "I'm exploring what's next" is true and enough. Don't lead with hardship (layoff, months of searching).
- Plain contractions, short sentences, no filler.

**Avoid:** "I hope this message finds you well," "I'd love to pick your brain," "reaching out because I'm passionate about," flattery stacks ("huge fan," "incredible work"), buzzword lists of tools, three asks, em-dash-heavy rhythm, and anything that reads as a template with the name swapped. If a sentence could be sent to any other leader unchanged, rewrite it.

**Example (placeholders shown where the user must supply real details):**

> Subject: Question about [specific platform topic] at [Company]
>
> Hi [First name],
>
> I read [specific thing: your team's post on X / your talk on Y] and the part about [specific detail] stuck with me. I'm a Senior SRE who spent the last couple of years [recent relevant experience, e.g. running on-call for a large cloud platform], so [related focus area] is where my head is at.
>
> I'm curious how your team is approaching [one concrete challenge]. Would you be open to a 15-minute video call sometime in the next couple of weeks? Totally fine if the timing's bad.
>
> Thanks,
> [Your name]

(Fill the experience line from a bullet on the candidate's resume. Swap in a different resume-backed line per recipient.)

### Step 3: Prompt for more detail

After the draft, always close with 2-4 specific prompts that would make the message more personal, chosen from what is still generic. Phrase them as questions the user can answer in a line, for example:

- "Is there a post, talk, or tool of theirs you've actually used? That would make a stronger first line than what I have."
- "Do you share anything with them (school, former employer, a mutual contact)? One true shared detail beats three polished sentences."
- "Which of these two credibility lines would they care about more: [A] or [B]?"
- "Want me to search for their recent public work to find a hook?"

Offer to revise once they answer. Do not pad with generic advice.

### Step 4: Follow-ups (offer, don't dump)

Offer these after the first draft is settled, and write them on request:
- **One nudge, 5-7 days later,** two sentences, adds a small new thing (an article, a relevant thought), not "just bumping this."
- **Thank-you within 24 hours of the chat,** referencing one specific thing they said, and what the user will do with it.
- **The soft referral ask,** used near the end of a good conversation rather than in the first message: "Is there anyone else on your team or in your network you'd suggest I talk to?" and, only if rapport is there, "If a role opens that fits, would you be open to pointing me to the right person?"

Suggest a lightweight tracker (name, company, date sent, nudge date, status) if the user is messaging more than a few people.

---

## Sections 2-4: Supporting inputs, ordered by what the market rewards today

The original source material listed four strategies. After checking current hiring data (`references/market-signals-2026.md`), the order below reflects what matters most right now. Use these to choose *what to say* and *who to message*, not as separate lectures.

### Section 2: Positioning for today's demand (highest priority after outreach)

Pick the credibility line from the themes hiring leaders are currently asking about. Fastest-growing requirements in 2026 sources: AI-assisted operations (AIOps), platform engineering and internal developer platforms, incident-management leadership, and cloud cost (FinOps). Match these to resume facts only:

- AIOps / automation: Python automation that reduced MTTR, self-healing runbooks, health checks, alert-noise work, and the resume's LLM observability/RAG work.
- Platform: onboarding service teams into environments, landing zones, Terraform/GitOps pipelines, self-service provisioning cut from days to hours.
- Incident leadership: Tier 3 escalation, on-call, RCA, 99.99% availability, 40% downtime reduction at Twilio.

Frame lines around impact (reliability, velocity, toil removed), not tool lists. If the user wants a stronger metric than the resume holds, ask them for the real number instead of estimating.

### Section 3: Choosing who to message

Prioritize in this order, and say why when suggesting targets:
1. **Regulated and large enterprises with growing tech hiring** (insurance, banking/finance, healthcare, defense/aerospace), where the resume has real depth (FedRAMP/IL5, MetLife financial services).
2. **Mid-market and growth-stage companies** (roughly 50-500 employees, Series B/C) that need their first or second dedicated platform/SRE hire. Smaller applicant pools; a leader may reply personally.
3. **Big Tech and household-name employers last.** Hyper-competitive loops and unpredictable headcount; worth a message only with a real connection.

Target the person who owns the problem: engineering manager of the platform/SRE team, director of platform or infrastructure, VP Engineering at smaller companies. Prefer companies whose stack overlaps the user's (Kubernetes, Terraform, ArgoCD, Datadog/Prometheus, AWS/OCI/GCP/Azure).

### Section 4: Public proof-of-work

With AI-polished resumes everywhere, leaders trust things they can inspect. When the user has a public artifact (a blog post, GitHub repo, open-source contribution, or a demo like the project's AIOps or lab builds), consider a single link in the follow-up message after a reply, not in the first message, so the first note stays a human ask rather than a pitch. Help the user pick one artifact that matches the recipient's problem. Only describe work the user has actually done.

---

## Output format

1. One line saying what you drafted and for whom.
2. The message variant(s), clearly labeled, ready to copy.
3. The Step 3 prompts.
4. Offer for follow-ups only if not yet drafted.

Keep commentary light. The message is the product.

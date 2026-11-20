# EdTech Placement Transparency & Reporting System

**A Business Analysis Portfolio Project by Hardik Pant**

### The Problem I'm Trying to Solve

Think about the last time you considered signing up for an EdTech program. Before handing over your money and your time, you'd want to know one thing above everything else: *will this actually help me get a job?*

Right now, answering that question is harder than it should be. Learners who are still deciding whether to join a program are left digging through testimonials, screenshots, and scattered posts.

Testimonials are valuable. They're real, verified experiences. But on their own, they don't tell you:

- Are companies *currently* hiring through this program?
- What roles are they hiring for, and what do they pay?
- What does the verified placement data actually tell us about learner outcomes?
- Are those placements for freshers, or people with experience?

So the prospective learner is basically asked to trust a highlight reel. That's the gap I'm trying to close.

I noticed this while working in EdTech admissions myself. I kept hearing the same question from prospects, and kept noticing that the honest answer lived in a portal they couldn't see. The information wasn't missing. It just wasn't reaching the person who needed it most. That's what made me want to dig in properly.

### What I Want to Achieve

My goal is simple: replace ambiguity with evidence. Specifically, I want to:

- Give prospective learners a transparent, structured view of placement outcomes.
- Show recent job opportunities so they can understand current hiring activity.
- Define placement metrics clearly and use verified data: no vague claims.
- Help people understand actual hiring trends and the experience levels of placed learners.

### The Solution I'm Designing

I've proposed a learner-facing dashboard supported by the organisation's official placement portal. It's built for the person who's still deciding, the one asking, "Is this program's placement record credible?"

The dashboard would include:

- **Recent job postings:** Opportunities listed on the official placement portal within the last 60 days, showing company name, location, job role, CTC, and posting date. Listing status distinguishes active, expired, and closed opportunities, with filters for location, role, CTC range, and work mode.
- **Verified placement metrics:** Average Annual CTC calculated using all verified learner placements, including independently secured placements, with the number of records behind it shown.
- **Experience-level placement distribution:** A graph showing the experience levels of learners placed through opportunities listed on the official placement portal. Experience is measured at the time of placement, including experience gained during the programme.
- **Transparent reporting:** Every metric has a clear definition, reporting period, and last-updated timestamp so learners can understand exactly what the numbers represent.
- **Registration with mobile OTP:** Visitors register and verify their number before viewing the dashboard, and their details flow into the CRM as a lead (existing leads are updated, not duplicated).

An important distinction: Average Annual CTC and the experience-level graph use different placement populations. The dashboard will explicitly communicate this to avoid misleading interpretations.

### Where the Risk Thinking Comes In

The more I worked on this, the more I realised that a transparency project can easily become a *misleading* project if the numbers aren't handled carefully. So a good chunk of the analysis is really about what could go wrong, and designing it out:

- **A "package" number can mislead.** So I defined a mean with a disclosed outlier caveat, salary ranges averaged by midpoint, internship stipends excluded, and the record count always visible.
- **Two populations can look like one.** Average CTC covers all verified placements, while the experience graph covers portal-facilitated ones only. Every metric carries a scope note.
- **Posting counts can be inflated.** Deliberate reposts count as separate events, accidental duplicate imports don't, and posting events are never confused with open vacancies or hiring partners.
- **Stale data erodes trust.** There's a last-updated timestamp, and if a refresh fails the last good data stays visible with its real timestamp.
- **Small groups can identify people.** The dashboard shows aggregates only, and a minimum cohort threshold is flagged for review before release.
- **Integrations can fail quietly.** If the CRM is down, access isn't blocked and the prospect isn't silently lost.

### The Work Behind It (The BA Stuff)

This isn't just a concept. I've been working through the business analysis required to support it, and most of the core documents now exist as drafts. Here's where the project stands:

| **Deliverable** | **Status** | **Where to find it** |
| :--- | :--- | :--- |
| Business Requirements Document (BRD v2.0) | **Working draft** | [`02-requirements`](02-requirements/) |
| Functional Requirements Document (FRD v1.0) | **Concise draft** | [`02-requirements`](02-requirements/) |
| Stakeholder analysis | **Draft** (section 6 of the BRD) | [`02-requirements`](02-requirements/) |
| Business rules and KPI definitions | **Draft** (BRD, FRD, use cases) | [`02-requirements`](02-requirements/) |
| Gap analysis (v1.1) | **Draft** | [`03-process-modelling`](03-process-modelling/) |
| AS-IS / TO-BE process flows | **Draft** | [`03-process-modelling`](03-process-modelling/) |
| Use-case diagram and descriptions | **Draft** | [`04-use-case-modelling`](04-use-case-modelling/) |
| Data dictionary and ERD | **Draft** | [`04-use-case-modelling`](04-use-case-modelling/) |
| Cross-document consistency review | **In progress** | n/a |
| User Acceptance Testing (UAT) | **Pending** | n/a |

### How I'm Going About It

I'm following a structured BA approach to make sure the solution actually solves the right problem, not just looks good on paper:

1. **Identify the problem:** Understand why prospective learners struggle to assess placement credibility.
2. **Map the stakeholders:** Identify who needs what, from prospective learners evaluating the programme to the placement team maintaining the data.
3. **Analyse requirements:** Define the information and functionality needed for a credible solution.
4. **Compare current and future states:** Document the existing information gaps (AS-IS) and the proposed transparent future state (TO-BE).
5. **Set the rules:** Define business rules and KPIs so the numbers are consistent and interpretable.
6. **Model the solution:** Design the dashboard, process flows, use cases, and data.
7. **Validate:** Test the requirements against the original business problem to ensure they address the identified gaps.

### Things I'm Still Working Out

I'd rather be upfront about the rough edges than pretend the work is finished:

- **Consistency across documents.** The documents were written at different stages, and a few details don't line up yet, such as the data refresh cadence (daily vs weekly) and whether visitors need periodic OTP re-verification. Reconciling these is my next task.
- **Open design decisions.** OTP attempt and resend limits, CRM retry rules, experience-band boundaries, data retention, and the minimum cohort size for privacy are all flagged as TBD rather than guessed.
- **Process flows.** The TO-BE flow shows the happy path well, but I still want to add OTP expiry/resend and CRM-failure paths, and show the placement team's role.
- **Testing.** UAT cases tied to the acceptance criteria are still ahead.

### Where I'm At

The project is currently in the **business requirements and solution design** phase. The requirements, process models, use cases, and data definitions are drafted. I'm now tightening them so they agree with each other, then moving on to UAT test cases.

I'm doing this alongside a full-time job, and I'm learning as I go. If you spot something that doesn't make sense, or have a better way of looking at it, I'd genuinely like to hear it.

*Quick note: This is an independent portfolio project based on a realistic but anonymised EdTech business scenario. It is not a deployed product. Any sample data used in the documents is illustrative, and any in future deliverables will be clearly identified as simulated.*

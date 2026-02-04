# Summary of Initiatives Document

This document catalogs the impact of various optimization initiatives, tracking time savings and cost reductions across different processes.

---

## Coach Workbook Optimizations

### InBody Weight and Body Fat Percentage Graphs

**Description:** InBody weight and body fat percentage graphs are now attached within the 360 dashboard, eliminating the need to manually access coach workbooks and PDFs for comparisons.

**Previous Process:**
- Time per client: **2.5 minutes**
- Steps: Log into coach workbooks, locate PDFs, perform comparisons

**New Process:**
- Time per client: **15 seconds**
- Steps: Direct access via 360 dashboard

**Time Savings Calculation:**
- Time saved per client: 2.5 minutes - 15 seconds = **2 minutes 15 seconds** (135 seconds)
- Clients per coach: **30**
- Frequency: **Once per week**
- Weeks per year: **52**

**Total Time Saved per Coach per Year:**
- Per client: 135 seconds
- Per week: 135 seconds × 30 clients = **4,050 seconds** (67.5 minutes)
- Per year: 4,050 seconds × 52 weeks = **210,600 seconds** = **3,510 minutes** = **58.5 hours**

**Cost Analysis (Average Coach Rate: $55/hour):**

**Before Optimization:**
- Time per client: 2.5 minutes = 0.04167 hours
- Cost per client: 0.04167 hours × $55 = **$2.29**
- Cost per week: $2.29 × 30 clients = **$68.70**
- Cost per year: $68.70 × 52 weeks = **$3,572.40**

**After Optimization:**
- Time per client: 15 seconds = 0.00417 hours
- Cost per client: 0.00417 hours × $55 = **$0.23**
- Cost per week: $0.23 × 30 clients = **$6.90**
- Cost per year: $6.90 × 52 weeks = **$358.80**

**Annual Cost Savings per Coach:**
- Time saved: 58.5 hours
- Cost savings: 58.5 hours × $55/hour = **$3,217.50/year**
- Alternative calculation: $3,572.40 (before) - $358.80 (after) = **$3,213.60/year**

---

### Session Attendance Tracking (e.g. Heat Map)

**Description:** Session attendance tracking—such as a heat map view—surfaces attendance data quickly in the 360 dashboard. This reduces time spent on page load and navigation, and cuts down on gym manager/coach questions about how to access this data. It also supports retention by giving managers fast visibility into who is (or isn’t) attending, so they can act before at-risk clients churn.

**Benefit 1: Time and Cost Savings (Page Load, Navigation, and “How do I access this?” Questions)**

**Previous Process:**
- Time per client: **3 minutes** (page load, navigation, and handling manager questions on how to access attendance data)
- Steps: Multiple systems, slow loads, repeated “how do I find this?” support

**New Process:**
- Direct visibility via dashboard (e.g. heat map); minimal navigation and fewer support questions

**Time Savings Calculation:**
- Time saved per client: **3 minutes** (180 seconds)
- Clients per coach/manager: **30**
- Frequency: **Once per week**
- Weeks per year: **52**

**Total Time Saved per Coach/Manager per Year:**
- Per week: 180 seconds × 30 clients = **5,400 seconds** (90 minutes)
- Per year: 5,400 seconds × 52 weeks = **280,800 seconds** = **4,680 minutes** = **78 hours**

**Cost Analysis (Average Coach/Manager Rate: $55/hour):**

**Before Optimization:**
- Time per client: 3 minutes = 0.05 hours
- Cost per client: 0.05 hours × $55 = **$2.75**
- Cost per week: $2.75 × 30 clients = **$82.50**
- Cost per year: $82.50 × 52 weeks = **$4,290.00**

**After Optimization:**
- Time per client: negligible (direct access)
- Cost per year (residual): **~$0** (assumed near-zero for this workflow)

**Annual Cost Savings per Coach/Manager:**
- Time saved: **78 hours/year**
- Cost savings: 78 hours × $55/hour = **$4,290/year**

---

**Benefit 2: Retention Improvement from Fast Data Visibility**

Faster visibility into session attendance allows managers to spot at-risk clients (e.g. dropping attendance) and intervene earlier, supporting retention.

**Base Assumptions:**
- Average membership: **$10,000 per 6 months** = **$20,000 per year** per client
- Current churn rate: **3%**
- Conservative estimate: **1 client saved from churning per sprint** (every 3 months) due to earlier intervention driven by session attendance visibility

**Retention Impact Calculation:**
- Sprints per year: 12 months ÷ 3 months = **4 sprints**
- Clients retained per year (attributed to this initiative): **1 per sprint** = **4 clients**
- Revenue retained per year: 4 clients × $20,000/year = **$80,000/year**

**Summary (Session Attendance Tracking):**
- **Operational savings:** **$4,290/year** per coach/manager (78 hours at $55/hr)
- **Retention benefit (conservative):** **$80,000/year** in retained revenue (4 clients × $20,000)
- **Combined annual benefit:** **$84,290/year** (before scaling across multiple coaches/managers)

---

### Coach Weekly Snapshots (Session Expectations vs Actuals)

**What it is:** A weekly view (e.g. `view_session_balance_adjusted_25` in Supabase) that shows, per coach, how many sessions/hours were **expected** (from role allocation and roster) versus how many were **actually** delivered—so expectations and actuals are in one place.

**How it works (simple):** Expected sessions per coach per week come from the roster and role allocations (e.g. FTE/PTE, leave, holidays). Actual sessions come from logged delivery (e.g. `coach_session_actual`). The view compares them and shows a **balance** (actual − expected) so you can see at a glance who’s ahead, on track, or behind.

**Simple diagram:**

```
┌─────────────────────────────────────────────────────────────────┐
│  COACH WEEKLY SNAPSHOT (expectations vs actuals)                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   EXPECTED (per coach, per week)     ACTUAL (per coach, per week) │
│   • From roster & role allocation   • From logged sessions        │
│   • Adjusted for leave/holidays    • By session type/duration    │
│         │                                    │                   │
│         └──────────────┬─────────────────────┘                   │
│                        ▼                                         │
│              BALANCE = actual − expected                         │
│              (ahead / on track / behind)                          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

**Benefit of tracking this (before vs after):**

- **Before:** Tracking was **very manual and ambiguous**—similar to relying on a loose HR or spreadsheet approach. Hours and sessions were not clearly defined or visible, which led to **decreased productivity**, **resentment**, and **ambiguity** about how numbers were calculated and who was doing what.
- **After:** Expectations and actuals are **transparent and visible** in one place. Each role has a **clear allocation of time**, so the question is **“Is this assigned to me?”** rather than “Am I being judged on unclear numbers?” Work feels **more fair and accounted for**, and there is **less resentment** across the team because everyone can see how expectations and delivery are defined and compared.

---

### Schedule Preferences (Collection, Heat Map, and Rolling Window)

**What it is:** Schedule preferences are collected in the `schedule_preferences` table and surfaced in Retool via a **heat map** per coach. Coaches can now see their own preferences, and there is a **12‑week rolling window** in which they can add or change preferences. Gym managers have been trained on the flow.

**What’s implemented:**
**How the rolling 12-week window works (in Supabase):**

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  SCHEDULE PREFERENCES – ROLLING 12-WEEK WINDOW                              │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  1. PERIODS (when coaches can submit)                                        │
│     Cron (every Monday 05:05)                                                 │
│            │                                                                  │
│            ▼                                                                  │
│     generate_schedule_periods()  ──────►  schedule_periods                     │
│     (lookahead 6w, 2-week blocks)        (week_start, week_end,               │
│                                           submission_deadline)                │
│                                                                              │
│  2. COACHES SUBMIT PREFERENCES                                                │
│     Retool (heat map / form)                                                  │
│            │                                                                  │
│            ▼                                                                  │
│     schedule_preferences                                                      │
│     (staff_id, period_id, block, preference_type, rank)                      │
│            │                                                                  │
│            │  trigger_sync_to_rolling (on INSERT)                              │
│            ▼                                                                  │
│     rolling_schedule_preferences                                              │
│     (effective_date = period's week_start, end_date = effective_date + 12w)      │
│                                                                              │
│  3. RETOOL HEAT MAP                                                           │
│     Reads schedule_preferences + schedule_periods (and/or rolling_*)          │
│     to show each coach their preferences across the rolling window.          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**What's implemented:**
- Preferences stored in `schedule_preferences` and mapped into Retool (heat map by coach).
- Visibility **per coach** so individuals can see and manage their own preferences.
- **12‑week rolling window** for coaches to submit and update preferences.
- Gym managers onboarded and using the system.

**Benefits:**
- **Perception of fairness** — Submitting and changing preferences is clear and visible, so the team feels the process is fair rather than opaque or favoring a few.
- **Better visibility for managers** — Managers can see preferences in one place (e.g. heat map) and use that to balance the roster and set expectations.
- **Scalability** — Less reliance on people “deep in the operational system”; the process can scale beyond a small number of power users.
- **Admin can own schedule build** — Opens the door for an **admin team member** to do the heavy lifting for a **monthly schedule build**, instead of it staying with a narrow set of operators.
- **Framework for communication** — Gives managers a clear basis to correct attitudes, set expectations, and maintain a **fair balance of preferences and coverage** across the team.

---

### New Sale Form (New Client Journey Failsafe)

**What it is:** A new system for handling every new sale, implemented as an N8n flow (the “new client – client journey failsafe”). The work involved **copying** the previous behaviour where possible and **creating a new system** so that new sales are processed consistently and with less manual admin.

**What was involved (simple):**
- **Copy:** Recreate the steps and logic from the old way of processing new sales (so nothing important was lost).
- **Create new:** Build a dedicated N8n flow that runs when a new sale comes through, so the same steps happen automatically and in a clear order (client journey failsafe).

So in practice: “copy” = bring over the right steps; “create new” = one clear N8n flow that runs those steps for every new sale.

**What the N8n flow does (from the flow):**

1. **Trigger:** New sale form submitted (Retool) → N8n **Webhook** receives the payload.
2. **Create / look up:** Create or get member in **member_database**; look up **RM profile**, **salesperson**, **membership type**, **nutrition lead**, **programming coach**, **add-ons**, **memberships** (Supabase).
3. **Client Journey Failsafe:** Append one row to **Google Sheets** ("Client Journey Failsafe" → sheet "New Sales") with client name, cohort dates (7 days, 30 days, 12 weeks), membership, RM, payment notes, and all journey checkpoints (physicals, calls, renewals, etc.).
4. **Supabase writes:** Create/update **member_memberships**, **member_addons**, **newsale metadata**, link **member_database** to coach (RM); **payment success tracker**; **biomap**; **member_myzone**; **member_health_metrics**; **member_programs** (where applicable).
5. **Notifications:** **Slack** to RM's workbook channel (new client summary); **Slack** to programming coach; **confirmation email**; **referral email** (if referred); **RM client workbook**; **Sales team** message; **Referral & app download** email; **Consults** message; **Master payment** message.

So in one run: one new sale → one row in the journey sheet, all DB records in place, and everyone notified. No manual copy-paste or hopping between tools.

**Flow diagram (N8n):**

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  NEW SALE FORM – CLIENT JOURNEY FAILSAFE (N8n flow)                          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  Retool (new sale form)                                                       │
│        │                                                                     │
│        ▼                                                                     │
│  [Webhook]  ───►  create member / lookups (RM, salesperson, membership,     │
│                    add-ons, nutrition lead, programming coach)                │
│        │                                                                     │
│        ├────────►  [Google Sheets] Client Journey Failsafe – New Sales        │
│        │           (one row: client, dates, membership, journey checkpoints)  │
│        │                                                                     │
│        ├────────►  [Supabase] member_memberships, addons, newsale metadata,   │
│        │           member_database (coach), payment tracker, biomap,         │
│        │           myzone, health_metrics, programs                           │
│        │                                                                     │
│        └────────►  [Slack + Email] RM channel, programming coach,            │
│                    confirmation, referral, sales team, consults, payment      │
│                                                                              │
│  BEFORE: ~20 min manual admin  →  AFTER: ~5–10 min (flow does the rest)      │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Cost–benefit (admin time per new sale):**

| | Before | After (conservative) | After (best estimate) |
|---|---|---|---|
| **Admin time per new sale** | **~20 minutes** | **~10 minutes** (half) | **~5 minutes** |
| **Time saved per sale** | — | **~10 minutes** | **~15 minutes** |

**Sales cost saved (admin time):**

| Assumption | Value |
|---|---|
| Sales team cost | **$65/hour** |
| New sales per month | **20** |

| | Conservative (~10 min saved/sale) | Best estimate (~15 min saved/sale) |
|---|---|---|
| **Time saved per month** | 20 × 10 min = **200 min** (3.33 hours) | 20 × 15 min = **300 min** (5 hours) |
| **Time saved per year** | 200 × 12 = **2,400 min** = **40 hours** | 300 × 12 = **3,600 min** = **60 hours** |
| **Cost saved per month** | 3.33 × $65 = **~$217** | 5 × $65 = **~$325** |
| **Cost saved per year** | 40 × $65 = **$2,600** | 60 × $65 = **$3,900** |

- **Conservative:** Admin time cut by at least half (20 min → ~10 min).
- **Best estimate:** Down to ~5 minutes per new sale (20 min → 5 min).

*To scale: multiply time saved per sale by number of new sales per month/year to get total admin hours saved. N8n flow details (e.g. JSON) can be added to this section or linked from a doc such as “test new client – client journey failsafe” once the file is in the repo.*

---


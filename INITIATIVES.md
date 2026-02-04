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

**Benefit 1: Time and Cost Savings (Page Load, Navigation, and "How do I access this?" Questions)**

**Previous Process:**
- Time per client: **3 minutes** (page load, navigation, and handling manager questions on how to access attendance data)
- Steps: Multiple systems, slow loads, repeated "how do I find this?" support

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

**How it works (simple):** Expected sessions per coach per week come from the roster and role allocations (e.g. FTE/PTE, leave, holidays). Actual sessions come from logged delivery (e.g. `coach_session_actual`). The view compares them and shows a **balance** (actual − expected) so you can see at a glance who's ahead, on track, or behind.

**Simple diagram:**

```
┌─────────────────────────────────────────────────────────────────┐
│  COACH WEEKLY SNAPSHOT (expectations vs actuals)                 │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   EXPECTED (per coach, per week)     ACTUAL (per coach, per week)│
│   • From roster & role allocation   • From logged sessions        │
│   • Adjusted for leave/holidays    • By session type/duration    │
│         │                                    │                    │
│         └──────────────┬─────────────────────┘                    │
│                        ▼                                          │
│              BALANCE = actual − expected                          │
│              (ahead / on track / behind)                          │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

**Benefit of tracking this (before vs after):**

- **Before:** Tracking was **very manual and ambiguous**—similar to relying on a loose HR or spreadsheet approach. Hours and sessions were not clearly defined or visible, which led to **decreased productivity**, **resentment**, and **ambiguity** about how numbers were calculated and who was doing what.
- **After:** Expectations and actuals are **transparent and visible** in one place. Each role has a **clear allocation of time**, so the question is **"Is this assigned to me?"** rather than "Am I being judged on unclear numbers?" Work feels **more fair and accounted for**, and there is **less resentment** across the team because everyone can see how expectations and delivery are defined and compared.

---


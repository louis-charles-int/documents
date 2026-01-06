# AllDayLoans & PingFree - Rebuild Plan 2026

**Team:** Pawas, Nitin (+ potential new developer)  
**Timeline:** 12 weeks (3 months)  
**Last Updated:** 06-01-2025

---

## 🎯 What We're Doing

Rebuild AllDayLoans and PingFree from scratch using modern 2026 technology:
- **AllDayLoans:** Next.js (frontend + API routes)
- **PingFree:** Laravel API (PHP) backend + Next.js admin panel
- **Database:** MySQL (upgraded to latest version)
- **Support:** UK + USA leads in one system
- **Multi-project:** Handle AllDayLoans, Yuploans, QuickCashDirect, and future projects

**Why:** Current PHP/HTML code is old, hard to maintain. Need USA support and better reporting.

---

## ✅ Key Decisions Needed

### 1. Technology Stack
- **Frontend:** React + Next.js + TypeScript
- **Backend:** Laravel API (PHP) + MySQL
- **Approach:** Modern JSON APIs (replacing old form posts)

**Question:** Confirm this tech stack is acceptable?

### 2. Timeline & Approach
- **12 weeks (3 months)** initial estimate
- **Staging after 2 weeks** - then iterative updates
- **Build in background** - no rush, replace when ready
- **Timeline is flexible** - will adjust based on:
  - Changing requirements
  - Number of developers available

**Question:** Is 3 months initial estimate acceptable? Any deadline constraints or flexibility needed?

### 3. Multi-Project Support
- One PingFree system handles multiple loan projects:
  - AllDayLoans (UK)
  - Yuploans (USA)
  - QuickCashDirect (USA) - future integration
  - Easy to add more projects later

**Question:** Confirm multi-project approach is correct?

### 4. Features to Keep
- All current features must work
- UK + USA lead support
- Better reporting (current reporting is basic)
- No data loss during migration

**Question:** Any features to add/remove/prioritize?

### 5. Resources
- **Team:** Pawas, Nitin (+ potential new developer)
- **Repos:** Separate Git repos for AllDayLoans and PingFree
- **Environments:** Staging + Production for each repo

---

## 📊 Current vs New

| Current | New |
|---------|-----|
| PHP/HTML | Next.js (React), Laravel API (PHP) |
| MySQL (old version) | MySQL (latest version) |
| UK only | UK + USA |
| Basic reporting | Advanced reporting |
| Single project | Multi-project support |

---

## ⚠️ Key Considerations

1. **Data Migration - Decision Needed:**
   - **Option A (Simpler):** Start fresh - keep old data in old PingFree system, new system starts storing data when it goes live
   - **Option B (More Complex):** Migrate all existing data from old system to new system
   
   **Question:** Which approach do you prefer? Start fresh or migrate all historical data?

2. **No Downtime:** Old system runs until new one is ready
3. **Testing:** Thorough testing before production deployment
4. **Staging First:** Deploy to staging after 2 weeks for early visibility

---

## 📅 Timeline Overview

- **Weeks 1-2:** Setup + initial staging deployment
- **Weeks 3-5:** Core features (iterative staging updates)
- **Weeks 6-8:** Admin panel + backend APIs
- **Weeks 9-10:** USA support + multi-project
- **Weeks 11-11.5:** Reporting + polish
- **Weeks 11.5-12:** Testing + migration prep + production deployment

---

## ✅ Next Steps (Pending Approval)

1. Review and confirm key decisions above
2. Prepare detailed technical specs (DB schema, API endpoints)
3. Set up Git repositories with staging/production environments
4. Start development

---

**Document Version:** 1.0  
**Status:** Ready for Discussion


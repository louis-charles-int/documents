# AllDayLoans & PingFree - Rebuild Plan 2026

**Team:** Pawas, Nitin (+ potential new developer)  
**Status:** Ready to Start  
**Timeline:** 16 weeks (4 months)

---

## 📋 Quick Overview

**What We're Doing:**
- Rebuilding AllDayLoans and PingFree from scratch using modern 2026 technology
- AllDayLoans: Next.js (frontend + lightweight backend API routes)
- PingFree: FastAPI (backend) + Next.js (admin frontend)
- Making it work for both UK and USA leads in one system
- **Multi-project support** - Can handle AllDayLoans (UK), Yuploans (USA), QuickCashDirect (USA), and future projects
- **Project-specific reporting** - Each project can view its own reports
- Improving reporting and making everything faster
- Modern admin panel for PingFree (replacing old PHP admin interface)

**Why:**
- Current code is old (PHP/HTML) and hard to maintain
- Need USA support (currently UK only)
- Need better reporting
- Need modern, maintainable code
- Need secure API key handling (server-side)

**How:**
- Build new system in background (no rush)
- Deploy to staging after 2 weeks, then update iteratively
- Replace old system when ready
- Keep all existing features, add new ones
- AllDayLoans uses Next.js API routes for security (API keys stay on server)

---

## 🎯 Project Goals

### Main Objectives

1. **Modernize Technology**
   - Replace old PHP/HTML code with modern stack
   - Use JSON APIs instead of form posts
   - Make code maintainable and scalable

2. **Unify UK & USA + Multi-Project**
   - One system handles both regions
   - One system handles multiple projects (AllDayLoans UK, Yuploans USA, QuickCashDirect USA, etc.)
   - One dashboard for reporting (with project filtering)
   - Project-specific views and reports
   - Same features for both regions and all projects

3. **Better Reporting**
   - Real-time dashboard
   - Better filters and exports
   - Custom reports

4. **Keep Everything Working**
   - All current features must work
   - No data loss
   - Smooth transition

---

## 📊 What Exists Now (Current System)

### AllDayLoans (Consumer Website)

**What it does:**
- People apply for loans online
- Multi-step form collects their information
- Sends leads to PingFree
- Tracks where visitors come from (Facebook, Google, etc.)

**Current technology:**
- PHP code
- HTML forms
- MySQL database
- Tracks: Google Analytics, Facebook Pixel, Hotjar, Clarity

**Key features to keep:**
- ✅ Multi-step loan application form
- ✅ Traffic source tracking (UTM parameters)
- ✅ Conversion tracking
- ✅ Email confirmations
- ✅ IP-based duplicate prevention
- ✅ Cookie consent
- ✅ Legal pages (Privacy, Terms, Complaints)
- ✅ Unsubscribe functionality

### PingFree (Lead Distribution System)

**What it does:**
- Receives leads from AllDayLoans (and other sources)
- Sends leads to lenders one by one (pingtree)
- If lender 1 says no, tries lender 2, then 3, etc.
- Tracks everything in admin panel
- Admin can view leads, reports, statistics, manage affiliates/lenders

**Current technology:**
- PHP code (backend + admin frontend)
- MySQL database
- Admin panel with many pages (dashboard, leads, reports, stats, charts, etc.)

**Key features to keep:**
- ✅ Sequential lender routing (pingtree)
- ✅ Affiliate management
- ✅ Lender management
- ✅ Custom lender trees per affiliate
- ✅ Commission tracking
- ✅ Lead tracking and reporting
- ✅ Email notifications
- ✅ SMS notifications (cron jobs)
- ✅ Partner integrations
- ✅ Admin dashboard with statistics
- ✅ Leads management interface
- ✅ Reports (processing log, errors, iframe views)
- ✅ Charts and visualizations
- ✅ User management
- ✅ System configuration

**What's missing:**
- ❌ USA lead support (UK only now)
- ❌ Good reporting (basic now)

---

## 🏗️ What We're Building (New System)

### Technology Stack (2026 Standards)

**AllDayLoans (Frontend + Lightweight Backend):**
- **Frontend:** React 18+ with Next.js 14+
- **Backend:** Next.js API Routes (lightweight server-side)
- TypeScript
- Tailwind CSS + shadcn/ui components
- **Why:** Single codebase, API keys stay secure, server-side validation

**PingFree (Backend + Admin Frontend):**
- **Backend:** FastAPI (Python 3.11+)
- **Frontend:** React 18+ with Next.js 14+ (Admin Panel)
- PostgreSQL 15+ database
- Celery + Redis for background tasks
- TypeScript for frontend
- Tailwind CSS + shadcn/ui components
- **Why:** FastAPI for powerful backend, Next.js for modern admin interface

**Why these choices:**
- Modern, maintainable, fast
- Good documentation and community support
- Easy to scale
- Secure (API keys hidden on server)

---

## 📐 How It Works

**Simple Flow:**
1. User fills loan form on AllDayLoans → submits to AllDayLoans API
2. AllDayLoans API validates, tracks IP, sends to PingFree
3. PingFree stores lead, tries lenders one by one (pingtree)
4. First lender to accept wins → user redirected to lender
5. Confirmation email sent to user

**Key Point:** AllDayLoans uses Next.js API routes to keep API keys secure on the server (never exposed to frontend).

---

## 🔧 What Needs to Be Built

### Project 1: AllDayLoans (Consumer Website)

**What to build:**
- Homepage with loan calculator
- Multi-step application form (7 steps: loan amount, personal info, address, employment, financial, bank, review)
- Legal pages (Privacy, Terms, Complaints)
- Tracking integration (Google Analytics, Facebook Pixel, Hotjar, Clarity)
- Cookie consent banner
- API routes for: lead submission, email sending, unsubscribe
- IP tracking for fraud prevention

**Tech:** Next.js 14+ (React + TypeScript), Tailwind CSS, React Hook Form + Zod validation

---

### Project 2: PingFree (Lead Distribution System)

**Backend (FastAPI):**
- Lead reception API (receives from AllDayLoans, Yuploans, QuickCashDirect, etc.)
- Lead storage (UK + USA, linked to projects)
- Routing engine (pingtree - tries lenders in order)
- Admin API endpoints (leads, reports, stats, affiliates, lenders, users, projects)
- Notifications (email, SMS via Celery)
- Automated tasks (scheduled reports, data cleanup)

**Admin Frontend (Next.js):**
- Dashboard with statistics and project switcher
- Project management (add/edit projects, assign affiliates)
- Leads management (view, filter, search, export)
- Reports (processing logs, errors, custom reports, exports)
- Statistics (leads, conversions, revenue, performance charts)
- Affiliate management (view, edit, custom lender trees, commissions)
- Lender management (view, edit, priorities, API endpoints)
- User management (roles, permissions, project access)
- System configuration

**Tech:** FastAPI (Python) + PostgreSQL, Next.js 14+ (React + TypeScript), Tailwind CSS

---

## 🗄️ Database Design

**Main Tables:**
- **projects** - Project/brand management (AllDayLoans UK, Yuploans USA, QuickCashDirect USA, etc.)
- **leads** - All loan applications (linked to project, region, affiliate)
- **lead_routes** - Tracks lender pings (order, status, responses)
- **lenders** - Lender configurations (region, API endpoints, priorities)
- **affiliates** - Affiliate accounts (linked to projects, API keys, commissions)
- **affiliate_lender_trees** - Custom lender trees per affiliate
- **config** - System configuration

---

## 🔌 API Integration

**AllDayLoans → PingFree:**
- AllDayLoans API routes handle lead submission securely (API keys on server)
- Sends to PingFree: `POST /api/v1/leads/submit`
- Includes: project_id, region, lead data (personal, address, employment, loan, bank, compliance, tracking)
- PingFree returns: success/declined status, redirect URL if accepted

**PingFree Admin API:**
- Endpoints for dashboard, leads, reports, stats, affiliates, lenders, users, projects
- All endpoints support project filtering

---

## 🇬🇧🇺🇸 UK & USA + Multi-Project Support

**Unified System:**
- One database handles all projects (AllDayLoans UK, Yuploans USA, QuickCashDirect USA, future projects)
- Each lead linked to project and region (UK/USA)
- Project-specific reporting (view by project or all)
- Easy to add new projects

**Example Projects:**
- **AllDayLoans** (UK) - Consumer loan application website, sends UK leads to PingFree
- **Yuploans** (USA) - WordPress-based USA loan application site, sends USA leads to PingFree
- **QuickCashDirect** (USA) - Next.js-based USA loan introduction service, currently uses Pingyo but will integrate with PingFree in the future

**UK:** Postcode validation, sort code, GBP, FCA/GDPR compliance  
**USA:** Zip code validation, routing number, USD, state rules, CCPA compliance  
**Routing:** UK leads → UK lenders, USA leads → USA lenders (same pingtree logic)

---

## 📈 Reporting

**Dashboard:** Overview metrics (leads, conversions, revenue) with project switcher  
**Lead Reports:** Filter by project, date, region, source, affiliate, lender, status - export to CSV/Excel/PDF  
**Performance Reports:** Affiliate/lender performance, UK vs USA comparison, project comparisons  
**Custom Reports:** Build, save templates, schedule reports (by project or all)

---

## 🔒 Security & Compliance

**Security:** JWT authentication, API key management, input validation, SQL injection/XSS protection, rate limiting, IP fraud prevention  
**Compliance:** UK (FCA, GDPR, ICO), USA (CCPA, state regulations), cookie consent, privacy policy, terms, data retention, audit logging

---

## 📅 Development Plan (16 Weeks)

### Phase 1: Setup & Initial Staging (Weeks 1-2)
- Set up development environment
- Design database schema
- Set up PostgreSQL, FastAPI, Next.js projects
- Create basic API endpoints
- Set up authentication
- **Deploy initial staging environment (Week 2)**

### Phase 2: Core Features & Iterative Staging Updates (Weeks 3-6)
- Build lead reception and storage
- Build routing engine (pingtree)
- Build homepage and multi-step form (AllDayLoans)
- Build API routes (submit-lead, send-email, unsubscribe)
- **Update staging weekly with completed features**

### Phase 3: Admin Panel & Backend APIs (Weeks 7-10)
- Build dashboard with statistics
- Build leads, reports, and statistics pages
- Build lender and affiliate management APIs
- Build admin API endpoints
- Build affiliate, lender, and user management
- **Update staging with each completed module**

### Phase 4: USA Support & Advanced Features (Weeks 11-12)
- Add USA support (validation, lenders)
- Add project management (AllDayLoans, Yuploans, QuickCashDirect)
- Integrate tracking (GA, FB, Hotjar, Clarity)
- Add email system and cookie consent
- **Update staging with USA features and multi-project support**

### Phase 5: Reporting & Polish (Weeks 13-14)
- Complete reporting features
- Add export functionality (CSV/Excel/PDF)
- Add custom report builder
- Add charts and visualizations
- Polish UI/UX
- Add monitoring and alerts
- **Final staging updates**

### Phase 6: Testing & Migration (Weeks 15-15.5)
- Unit, integration, and security tests
- Create migration scripts
- Test data migration
- User acceptance testing
- Bug fixes

### Phase 7: Production Deployment (Week 16)
- Final testing in staging
- Deploy to production
- Monitor and support

---


## ✅ Success Criteria

**Must work:** All current features, UK/USA leads, reporting, admin panel, no data loss, faster performance, regulatory compliance  
**Must be better:** Better reporting, faster performance, easier to maintain, better UX

---

## 🚨 Important Notes

**Keep:** All existing features, all data, all integrations, all compliance  
**Improve:** Modern code, better performance, better reporting, USA support  
**Don't:** Break features, lose data, skip testing, rush deployment

---

## 📝 Next Steps

1. **Review plan** with team and manager
2. **Prepare technical details** for the team:
   - Initial database relationships and schema design
   - Suggested API endpoints and request/response formats
3. **Set up development environment**
4. **Set up Git repositories** for each project:
   - AllDayLoans repository
   - PingFree repository
   - Configure staging and production environments for each repo
5. **Start Phase 1** (Setup & Core Infrastructure)
6. **Weekly progress reviews**
7. **Build in background** (no rush)
8. **Test thoroughly** before going live
9. **Deploy when ready**

**Estimated Time:** 16 weeks (4 months)

---

**Document Version:** 1.0  
**Last Updated:** 16-12-2025  
**Status:** Ready for Discussion

# CAP RUMAH 2026 - PROJECT OVERVIEW

## Project Metadata
- **Project Name:** Cap Rumah 2026
- **Product:** Toko App (Mobile) & CMS Web App
- **Program Description:** Exclusive loyalty program for high-performing retail stores
- **Start Date:** March 9, 2026
- **Status:** In Development
- **Force Update:** Yes
- **Release Method:** App Store & Google Play (Mobile), Web Deploy (CMS)
- **Last Updated:** May 15, 2026

---

## Project Goal
Implement CAP RUMAH as an integrated engagement program to manage and maintain retail store loyalty in a more structured and data-driven manner. The program aims to encourage consistent ordering from retail stores while providing monitoring tools for business performance.

---

## The Problem We're Solving
- Retail competition is intensifying with increased competitor penetration
- Risk of loyalty shift, especially among high-sales outlets (Pareto)
- Need for structured approach to manage relationships and performance at retail level
- Current system lacks data-driven monitoring for retail performance and growth

---

## Who Can Join?

### Eligible Existing Stores
- Registered since 2018 or earlier until Cap Rumah 2026 implementation
- Completed matchmaking with Djabesmen brand
- Matchmaking status: Accepted by at least 1 distributor
- Store category: Retail only (exclude: customer, project, developer, contractor)
- Store data type: Real

### Regional Coverage
- Program applies to stores in Java and Lampung regions (per master list)
- Stores outside these regions: registration only via data injection (special case)

### New Registered Stores
- Cannot access floating button yet
- Access granted after official registration and Djabesmen brand matchmaking

### Non-Participants
- Stores not meeting criteria have no access to Cap Rumah dashboard
- Floating button auto-hides without app refresh

---

## How to Win?

### Target Achievement
- **Goal:** Buy 220 tons of products during January 1 - December 31, 2026
- **Order Sources:** Toko App, Salesman App, DTO (Selling Out 2.0 Service)
- **Excluded:** Manager App orders, Genteng & Djabeskrup items
- **Order Status:** Partial and Closed only
- **Transparency:** Progress bar shows up to 220 tons; full history available in order history

---

## What Winners Get?
- Free exclusive tour for 2 people
- Destinations and administrative details announced by Djabesmen
- Tax deduction applied directly by organizer
- Required to update ID information to claim prize

---

## What Developers Are Building

### 1. Floating Button & Navigation
- New design floating button on homepage
- Directs to "Promo Eksklusif DBO Untung" (Exclusive Promo) dedicated page
- Shows navigation cards based on store eligibility
- Cap Rumah card appears first (if eligible)
- Bintang Rucika card appears below (disabled if not eligible)

### 2. Program Eligibility Check
- System automatically checks store eligibility
- Displays only eligible program cards
- Access rules based on store type, category, matchmaking, and regional area

### 3. Cap Rumah Dashboard
- Header image and program information
- Membership status information
- Progress tracking toward 220-ton target with visual progress bar
- Breakdown of order information

### 4. Program Information Section
- "What is Cap Rumah?" explanation
- Benefits overview
- General terms & conditions
- Rules and administrative requirements

### 5. Winner Status Display
**Winner Section** (Manual Data Injection)
- Shows winner status when injected by MIS
- Does not display automatically
- Includes CTA button and additional information

**Not Meeting Criteria Section**
- Shows only when confirmed by product team
- Displays after MIS verification and official notification

**Under Verification Section**
- Shows when winner data is being verified by MIS

### 6. Winner Document Upload
- Triggered when store is marked as winner
- Upload button appears on dashboard
- Mobile app interface with document requirements

### 7. Winner Document Submission (Mobile App)

**Store Information (Auto-filled)**
- Store owner name, store name, address (from login account)

**Store Documents**
- NPWP upload: JPG/PNG, max 25 MB (camera access)
- KK upload: PDF, max 10 MB

**Winner/Participant Information** (2 sections for 2 participants)
- Toggle option: "I am store owner" (auto-fills name & phone)
- Full participant name (mandatory, max 100 characters)
- Phone number (mandatory, max 13 digits, format 08...)
- KTP upload: JPG/PNG, max 25 MB (camera access)
- Passport upload: PDF, max 10 MB
- Photo passport: JPG/PNG, max 3 MB
- Collapsible: "How to Upload Passport" guide

**Checklist Section**
- Participant name (auto-filled)
- 3 mandatory questions with multiple choice answers
- Confirmation checkbox required before submission

### 8. Data Verification & Management
- All uploaded data goes to CMS Verification Program Loyalty
- Unverified data triggers popup on homepage for re-upload
- Only incorrect documents need re-upload (not all)
- Checklist must be re-completed for re-upload
- Database storage for ongoing multi-year program support
- Logging system for issue tracking

---

## Team
| Role | Name | Team |
|------|------|------|
| Product Analyst | Renita Salshabila | DBO |
| Business Analyst | Jeren Novita Hutagalung | DBO |
| UI/UX Design | Rudi Okmala | DBO |
| Project Manager | Sari | Kodefox |
| Tech Lead & Engineers | Adrian M | Kodefox |
| QA | Adam | DBO |

---

## Related Links
- [Jira Ticket: TAD-2452](https://dbo-id.atlassian.net/browse/TAD-2452?search_id=838d2945-f7d5-478c-aa5c-4f4e45994d02)

---

## Notes for Future Reference
- Participant list resets yearly (fresh start every January)
- Store category strictly retail only; special stores excluded
- Order sources: Toko App & Salesman App & DTO only (not Manager App)
- Regional coverage: Java & Lampung (special cases via data injection)
- Winner data manually injected by MIS (not automatic)
- Program covers period January 1 - December 31, 2026
- Store remains participant even if distributor connection lost (per rules)
- Progress bar caps at 220 tons display (full history in order history)
- All document uploads subject to size and format validation
- CMS verification required before prize eligibility confirmed

---

**Last Updated:** May 15, 2026 by SaritaPutri25
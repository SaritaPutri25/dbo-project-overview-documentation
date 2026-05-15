# CAP RUMAH 2026 - PROJECT OVERVIEW

## Project Metadata
- **Project Name:** Cap Rumah 2026
- **Product:** Toko App (Mobile)
- **Project Manager:** Sari (Kodefox)
- **Product Analyst:** Renita Salshabila (DBO)
- **Business Analyst:** Jeren Novita Hutagalung (DBO)
- **Start Date:** March 9, 2026
- **Status:** In Development
- **Expected Release:** End of May 2026
- **Last Updated:** May 15, 2026

---

## Project Goal
Cap Rumah is an exclusive loyalty program designed to manage and maintain store loyalty more effectively. The program aims to drive sustainable growth by increasing transaction consistency and retail engagement through a structured, data-driven approach.

---

## The Problem We're Solving
- Retail competition is intensifying due to direct and indirect competitor penetration
- Current system lacks a structured approach to manage retail relationships and performance
- Need for better monitoring and evaluation of retail performance based on data
- Risk of loyalty shift among high-contributing stores (Pareto outlets)

---

## Who Can Join?

### Eligible Stores
- **Region:** Jawa and Lampung only (as per master list region)
  - Stores outside this region can join only through special data injection
- **Existing Stores:** Must meet ALL conditions:
  - Registered since 2018 or before Cap Rumah 2026 implementation
  - Must complete matchmaking with Djabesmen brand
  - Matchmaking status: Accepted by at least 1 distributor
  - Store category: Retail only (exclude: customer, project, developer, contractor)
  - Store data type: Real
  - Note: If a store loses distributor connection during 2026, they remain as participant with access

### New Registered Stores
- Cannot access floating button initially
- Access granted after official registration and Djabesmen matchmaking completion

### Non-Participants
- Stores not meeting criteria above have no access
- Floating button automatically hides without needing refresh/logout

---

## How to Win?

### Target
- **Purchase Goal:** 220 Ton of products during January 1 - December 31, 2026
- **Calculation Rules:**
  - Only orders from Toko App, Salesman App, and DTO count (Manager App excluded)
  - Order status: Partial and Closed only
  - Excludes Genteng and Djabeskrup items
  - Progress bar shows maximum 220 Ton (detailed history available in Order History feature)

### Winner Determination
- No lottery system - automatic qualification upon meeting requirements
- Data is manually verified and injected by MIS team
- Not automatic calculation

---

## What Winners Get?

- Exclusive tour for 2 people
- Tour tax deduction applied directly by organizer
- Destination details and administrative requirements announced later by Djabesmen

---

## What Developers are Building

### 1. Floating Button & Navigation
- New floating button design on homepage
- Directs to dedicated page: "Promo Eksklusif DBO Untung"
- Shows navigation cards for eligible programs:
  - Cap Rumah (top card) - active if eligible
  - Bintang Rucika (below) - disabled if not eligible
- Card visibility based on eligibility rules
- Automatic hiding for non-participants

### 2. Dashboard Header
- Program header image
- Participant status information
- Clear eligibility messaging

### 3. Achievement Progress Bar
- Shows purchase progress towards 220 Ton target
- Breaks down by product categories
- Updates based on orders from Toko/Salesman App/DTO
- Period: January 1 - December 31, 2026

### 4. Benefits Section
- "Apa itu Cap Rumah?" explanation
- Benefits image display
- General terms and conditions ("Ketentuan Umum Cap Rumah")
- FAQ section
- CTA button for more information

### 5. Winner Information Section
- **Status 1:** Winner announcement with tour details
- **Status 2:** Non-winner notification (shown after MIS confirmation)
- **Status 3:** Verification in progress message
- Data shown only after MIS injection (not automatic)

### 6. Document Upload (Mobile App)
- **For Store Owner:**
  - Auto-filled profile (store name, owner name, address)
  - NPWP upload (jpg/png, max 25 MB)
  - Family Card (KK) upload (PDF, max 10 MB)

- **For Each Participant (1 or 2):**
  - Full name (mandatory, max 100 characters)
  - Phone number (mandatory, max 13 digits, format 08)
  - KTP photo (mandatory, jpg/png, max 25 MB)
  - Passport scan (mandatory, PDF, max 10 MB)
  - Passport photo (mandatory, jpg/png, 3 MB)
  - Toggle to auto-fill owner details

### 7. Verification Checklist & Confirmation
- Mandatory checklist questions (multiple choice)
- Confirmation checkbox before submission
- Validation messages for incomplete data

### 8. Data Verification & Re-upload
- All documents verified in CMS Verification Program Loyalty
- If rejected: popup notification on homepage
- Winners must re-upload rejected documents only
- Re-upload does not require recompleting entire checklist
- Status updates shown on dashboard

---

## Team
| Role | Name | Team |
|------|------|------|
| Product Analyst | Renita Salshabila | DBO |
| Business Analyst | Jeren Novita Hutagalung | DBO |
| Project Manager | Sari | Kodefox |
| Tech Lead | Adrian M | Kodefox |
| UI/UX Design | Rudi Okmala | DBO |
| QA | Adam | DBO |

---

## Related Links
- [Jira Ticket: TAD-2452](https://dbo-id.atlassian.net/browse/TAD-2452?search_id=838d2945-f7d5-478c-aa5c-4f4e45994d02)

---

## Notes for Future Reference
- Participant list resets yearly (everyone starts fresh in 2027)
- Region is strictly Jawa & Lampung; special stores excluded
- Order sources: only Toko App, Salesman App, and DTO count
- Items excluded: Genteng and Djabeskrup
- Winner data is manually injected, not automatic
- Changed requirement (May 6, 2026): Cap Rumah card appears first in floating button, Bintang Rucika card appears below and disabled
- System checks eligibility automatically based on store type, category, matchmaking, and region
- Verification process happens in CMS system, not in app
- Large file upload warning popup appears for files exceeding limits

---

**Last Updated:** May 15, 2026 by SaritaPutri25
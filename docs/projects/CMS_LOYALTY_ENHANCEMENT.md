# CMS PROGRAM LOYALTY ENHANCEMENT - PROJECT OVERVIEW

## Project Metadata
- **Project Name:** CMS Program Loyalty Enhancement
- **Product:** CMS Platform (Web)
- **Scope:** Bintang Rucika 2026 & Cap Rumah 2026
- **Status:** In Development
- **Last Updated:** May 15, 2026

---

## Project Goal
We're building a flexible CMS system that can handle multiple loyalty programs (like Bintang Rucika and Cap Rumah) all in one place. Right now the system only works for one program, which causes manual work and separate systems. We need to fix this to be more efficient and scalable.

---

## The Problem We're Solving
- Current CMS only works for Bintang Rucika 2025
- New programs coming in 2026 (Cap Rumah, etc.) can't use the same system
- Forces teams to do manual work or build separate systems
- Makes it hard to manage winner data in one place

---

## What Developers Are Building

### 1. Program Selection & Navigation
- Admins pick which loyalty program to work on
- Filter by year to see programs from different years
- Each program has its own separate dashboard
- Navigation breadcrumbs to go back to main page

### 2. Three Verification Stages

#### WAITING Tab (New Submissions)
- Stores upload their data
- No one has claimed it yet
- Shows date when store uploaded the data
- Once someone claims it → moves to IN PROGRESS

#### IN PROGRESS Tab (Being Checked)
- Data that's been claimed and is being worked on
- Has 3 different statuses within this tab:
  - **Status: In Progress** - Being checked, ongoing work (Blue button, "Verifikasi" action)
  - **Status: Unverified** - Checked but has issues, store must fix (Red button, grey action button, "Lihat Detail")
  - **Status: Revalidation** - Store has fixed & resubmitted data (Orange button, "Verifikasi" action)
- Only the person who claimed it can edit (prevents multiple people working on same data)
- Shows who claimed it and who last verified it
- Shows date of last change

#### VERIFIED Tab (Done)
- Successfully verified data
- View-only (can't change anything)
- Staff can only see details

### 3. Search & Filter (Works Per Tab)
- Search by store name or store code in one search box
- Filter by city/district (pick one, multiple, or all)
- Filter by date range
- All filters only affect the current tab you're looking at
- Doesn't affect other tabs

### 4. Export Data
- Download Excel files from each tab
- File includes only data from current tab + any filters applied
- Filename format: Data Pemenang - [Tab] - [Program] - [Year]
- Example: Data Pemenang - Tab Waiting - Bintang Rucika - 2025
- Shows warning popup before downloading large files

### 5. Counts & Visibility
- Shows total unique stores across all tabs
- Shows unique stores per tab
- Only counts stores that submitted data (not total winners)
- Example: If 300 are winners but only 200 submitted, CMS shows 200

### 6. Pagination
- Shows X rows per page (configurable)
- Works per tab (each tab has its own page numbers)
- Adjusts when filters are applied

---

## Related Links
- [Jira Ticket: TAD-2452](https://dbo-id.atlassian.net/browse/TAD-2452?search_id=838d2945-f7d5-478c-aa5c-4f4e45994d02)

---

**Last Updated:** May 15, 2026 by SaritaPutri25
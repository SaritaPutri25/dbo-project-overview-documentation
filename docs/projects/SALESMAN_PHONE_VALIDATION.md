# SALESMAN PHONE NUMBER VALIDATION - PROJECT OVERVIEW

## Project Metadata
- **Ticket:** TAD-2384
- **Project Name:** Salesman Phone Number Validation in CMS and Mobile App
- **Product:** Mobile App (Store Registration) & CMS Web Platform
- **Scope:** Super Admin, Regular Verification Admin, Store Registration Flow
- **Status:** In Development
- **Last Updated:** May 25, 2026

---

## Project Goal

Prevent stores from registering or being edited with a phone number that already belongs to a salesman. The validation applies across the Mobile App (store registration flow) and CMS (both Super Admin and Regular Verification Admin roles).

---

## The Problem We're Solving

- A store's phone number could accidentally be set to a number already registered as a salesman's number
- This caused data conflicts and made it hard to distinguish store contacts from salesman contacts
- There was no real-time warning to users when entering a duplicate number
- The issue affected both new store registrations (Mobile App) and store edits done by CMS admins

---

## What Developers Are Building

### 1. Mobile App — Store Registration Validation

Validation is triggered **after the user finishes typing** a phone number (on blur / field exit).

#### Page 1 – Detail Toko (Store Details)
- **Field:** No WhatsApp Anda (Your WhatsApp Number)
- **Validation message:** `Nomor sudah terdaftar sebagai Salesman`
- Shown in red below the field if the number matches an existing salesman number

#### Page 2 – Detail Anda (Your Details)
- **Field:** No WhatsApp Anda (Your WhatsApp Number)
- **Validation message:** `Nomor sudah terdaftar sebagai Salesman`
- Shown in red below the field if the number matches an existing salesman number

---

### 2. CMS — Store Edit Validation

Validation applies to **both Super Admin and Regular Verification Admin** roles when editing store phone numbers.

> ✅ **Confirmed:** The validation also applies to regular verification admins, not only super admins. The UI may differ between roles (super admin has a different edit UI for Owner phone number), but the validation behavior is the same.

#### Fields validated (on the Informasi Toko / Store Information form):
| Field | Error Message |
|---|---|
| Telepon Toko (Store Phone) | `Nomor sudah terdaftar sebagai Salesman` |
| Telepon Pengguna (User Phone) | `Nomor sudah terdaftar sebagai Salesman` |

- Validation is triggered **after the user finishes entering** the phone number
- Error message is shown in red below the respective field
- Applies to both Super Admin and Regular Verification Admin

---

## Validation Rules Summary

| Platform | Page / Form | Field | Trigger | Error Message |
|---|---|---|---|---|
| Mobile App | Page 1 – Detail Toko | No WhatsApp Anda | On blur (field exit) | Nomor sudah terdaftar sebagai Salesman |
| Mobile App | Page 2 – Detail Anda | No WhatsApp Anda | On blur (field exit) | Nomor sudah terdaftar sebagai Salesman |
| CMS | Informasi Toko (Master Edit) | Telepon Toko | On blur (field exit) | Nomor sudah terdaftar sebagai Salesman |
| CMS | Informasi Toko (Master Edit) | Telepon Pengguna | On blur (field exit) | Nomor sudah terdaftar sebagai Salesman |

---

## Related Links
- [Jira Ticket: TAD-2384](https://dbo-id.atlassian.net/browse/TAD-2384)

---

**Last Updated:** May 25, 2026 by SaritaPutri25

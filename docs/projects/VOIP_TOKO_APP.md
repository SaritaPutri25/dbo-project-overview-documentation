# VOIP IMPLEMENTASI - PROJECT OVERVIEW

## Project Metadata
- **Project Name:** Implementasi VOIP
- **Product:** Toko App (Mobile App) & Toko App CMS Verifikasi (Web App)
- **Version:** V1
- **Created Date:** June 15, 2026
- **Status:** In Development
- **Force Update:** Yes
- **Release Method:** Web App: Deploy ke Prod | Mobile App: App Store & Google Play
- **Last Updated:** June 15, 2026

---

## Team
| Role | Name | Team |
|------|------|------|
| Product Analyst | Renita Salshabila | Toko App |
| Project Manager | Sari | Kodefox (sari@kodefox.com) |
| Tech Lead & Engineers | Adrian M | Kodefox (adrianm@kodefox.com) |
| QA | Adam | DBO |
| BA | Jeren Novita Hutagalung | DBO |

---

## Applications & Affected Users
- Toko App - Mobile App
- Toko App - CMS Verifikasi Web App

---

## Project Goal
Meningkatkan keberhasilan verifikasi toko sehingga lebih banyak toko dapat bertransaksi secara mandiri melalui aplikasi dan mengurangi ketergantungan pada proses order manual.

---

## The Problem We're Solving
- Proses verifikasi toko mengalami hambatan karena banyak toko tidak mengangkat telepon dari admin verifikasi
- Nomor telepon yang digunakan belum memiliki identitas perusahaan (flag/masking caller ID)
- Toko menganggap panggilan sebagai spam atau penipuan
- Tingkat keberhasilan verifikasi toko menjadi rendah
- Target verifikasi toko tidak tercapai
- Toko yang belum terverifikasi tidak dapat melakukan transaksi pemesanan melalui aplikasi
- Toko tetap bergantung pada salesman atau distributor untuk pembuatan order
- Adopsi dan pemanfaatan aplikasi oleh toko menjadi tidak optimal

---

## Solution
Mengimplementasikan layanan caller identification (flag/masking nomor telepon) pada nomor yang digunakan oleh admin verifikasi sehingga identitas perusahaan dapat muncul saat toko menerima panggilan.

Perubahan yang diharapkan:
- Toko lebih mudah mengenali bahwa panggilan berasal dari pihak resmi perusahaan
- Meningkatkan kepercayaan toko untuk mengangkat telepon
- Memperlancar proses verifikasi toko
- Meningkatkan jumlah toko yang berhasil diverifikasi
- Mendorong penggunaan aplikasi sebagai kanal pemesanan mandiri oleh toko

---

## What Developers Are Building

### 1. CMS Verifikasi — Un-disabled Akses Data Owner (TAD-2535)

**User Story:**
Sebagai Admin Verifikasi, saya ingin dapat melihat data owner yang telah diajukan oleh toko meskipun proses verifikasi toko belum selesai, sehingga saya dapat melakukan pengecekan awal terhadap kelengkapan dan kesesuaian data owner tanpa harus menunggu proses verifikasi toko selesai.

**Acceptance Criteria:**
- Admin Verifikasi dapat melihat data owner yang telah diajukan oleh toko meskipun proses verifikasi toko belum selesai
- Data owner hanya dapat diakses dalam mode viewer — tidak dapat diedit maupun diverifikasi sebelum toko menyelesaikan proses verifikasi toko
- Saat Admin Verifikasi klik nama toko, sistem menampilkan pop-up detail data owner yang diajukan
- Admin Verifikasi dapat melihat informasi owner beserta lampiran swafoto dan kartu identitas pada halaman detail data owner

---

### 2. Mobile Toko App — Fitur Panggilan VoIP (TAD-2461)

**User Story:**
Sebagai Toko, saya ingin dapat menghubungi Admin Verifikasi melalui aplikasi, melihat status panggilan, dan mengakses riwayat panggilan, sehingga saya dapat berkomunikasi terkait proses verifikasi serta mengetahui status dan riwayat komunikasi yang telah dilakukan.

**Acceptance Criteria:**

#### Entry Point (Memulai Panggilan)
Toko dapat menghubungi Admin Verifikasi melalui tombol yang tersedia pada:
- Halaman **Product Tour**
- Halaman **Akun Saya**

#### Product Tour
- Activity: Verifikasi Toko
- Product tour tampil setelah user selesai upload foto toko, dan tampil juga di Akun Saya sebagai tampilan product tour
- User dapat melihat pop-up konfirmasi saat klik tombol "Telepon Sekarang"
- User dapat terhubung ke MicroSIP dan melihat status panggilan setelah memilih "Telepon Sekarang"

#### Akun Saya
- Activity: Verifikasi Toko dan Verifikasi Owner
- **Akses Telepon Verifikasi Toko:** Button ditampilkan selama proses verifikasi toko berlangsung dan akan disembunyikan ketika status verifikasi toko berubah menjadi "Verified"
- **Akses Telepon Verifikasi Owner:** Button ditampilkan setelah user mengajukan verifikasi owner dan akan disembunyikan ketika status verifikasi owner berubah menjadi "Verified"

#### Riwayat Telepon (Call Log)
- Panggilan Masuk Diterima (telepon dari admin ke toko)
- Panggilan Masuk Ditolak (telepon dari admin ke toko)
- Panggilan Masuk Tidak Diangkat (telepon dari admin ke toko)
- Panggilan Keluar Diterima (telepon dari toko ke admin)
- Panggilan Keluar Ditolak (telepon dari toko ke admin)
- Panggilan Keluar Tidak Diangkat (telepon dari toko ke admin)

#### Call Status Information
- **Queuing:** Jika Admin Verifikasi sedang menangani panggilan lain, Toko masuk ke antrian tunggu maksimal 3 menit. Sistem menampilkan status antrian. Backend memastikan antrian berdasarkan urutan siapa yang lebih dahulu telepon ke admin.
- **Tidak Terhubung:** Waktu tunggu panggilan melebihi 3 menit, koneksi internet tidak tersedia/tidak stabil, atau terjadi kegagalan koneksi saat proses menghubungkan panggilan.
- **Terhubung:** Panggilan berhasil tersambung; toko sedang terhubung dengan Admin Verifikasi.

#### Blocked Access
- Akses telepon dari Mobile Toko tidak dapat dilakukan setiap hari **Sabtu dan Minggu**
- Saat toko klik "Telepon Sekarang" di hari tersebut, sistem menampilkan pop-up pemberitahuan
- Berlaku untuk touchpoint: Product Tour dan Akun Saya

#### Permission
- Aktifkan permission untuk inbound call (telepon masuk) dari MicroSIP ke Mobile Toko App
- Aktifkan permission untuk outbound call (telepon keluar) dari Mobile Toko App ke MicroSIP (Admin Verifikasi)
- Permission terhadap aktivasi microphone
- Permission mengenai akses telepon inbound dan outbound jika user inaktif push notifikasi atau kill apps

---

### 3. Integrasi MicroSIP (TAD-2461)

**User Story:**
Sebagai Toko dan Admin Verifikasi, saya ingin dapat saling terhubung melalui fitur panggilan VoIP, sehingga proses komunikasi dan verifikasi dapat dilakukan secara langsung tanpa menggunakan media komunikasi di luar sistem.

**Acceptance Criteria:**

- **Admin Verifikasi → Toko:** Saat Admin Verifikasi melakukan panggilan melalui MicroSIP, sistem menghubungkan panggilan ke aplikasi mobile Toko. Toko dapat menerima panggilan dari Admin Verifikasi melalui aplikasi mobile Toko.
- **Toko → Admin Verifikasi:** Saat Toko melakukan panggilan melalui aplikasi mobile Toko, sistem menghubungkan panggilan ke MicroSIP yang digunakan oleh Admin Verifikasi. Admin Verifikasi dapat menerima panggilan dari Toko melalui MicroSIP.

---

### 4. Google Analytics Tracking

**Touchpoints yang di-track:**

| Touchpoint | Metrics |
|---|---|
| Product Tour → Pop Up "Telepon Sekarang" | Event count, active users, average engagement time per session; identifikasi user berdasarkan nomor HP dan kode toko |
| Akun Saya → Verifikasi Toko → Pop Up "Telepon Sekarang" | Event count, active users, average engagement time per session; identifikasi user berdasarkan nomor HP dan kode toko |
| Akun Saya → Verifikasi Toko → Riwayat Telepon | Event count, active users, average engagement time per session; identifikasi user berdasarkan nomor HP dan kode toko |
| Akun Saya → Verifikasi Owner → Riwayat Telepon | Event count, active users, average engagement time per session; identifikasi user berdasarkan nomor HP dan kode toko |

---

## Related Links
- [Jira Ticket: TAD-2535](https://dbo-id.atlassian.net/browse/TAD-2535) — CMS Verifikasi
- [Jira Ticket: TAD-2461](https://dbo-id.atlassian.net/browse/TAD-2461) — Mobile Toko App & Integrasi MicroSIP

---

## Change Request
| No | Date | Description |
|----|------|-------------|
| - | - | - |

---

## Notes
| No | Date | Attendees | Notes |
|----|------|-----------|-------|
| - | - | - | - |

---

## Plan of Implementation
| No | Activity | Note |
|----|----------|------|
| - | - | - |

---

**Last Updated:** June 15, 2026 by SaritaPutri25

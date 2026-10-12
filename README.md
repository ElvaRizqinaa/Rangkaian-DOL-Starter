# Dasar Kontrol Motor Listrik, DOL Starter, dan Simulasi CADe_SIMU

Repositori ini berisi materi pembelajaran, dokumentasi, dan file simulasi untuk **Pertemuan 2 Praktikum Mesin-Mesin Listrik**. Materi ini berfokus pada pemahaman sistem kendali elektromagnetik, perancangan rangkaian *Direct On Line* (DOL) Starter, serta pengujian simulasi menggunakan perangkat lunak CADe_SIMU.

---

## Pokok Bahasan Materi

### 1. Konsep Dasar Kontrol Motor Listrik
Sistem kontrol motor listrik merupakan sekumpulan peralatan yang dirancang untuk mengatur, mengarahkan, dan melindungi kinerja motor listrik (mulai dari proses *starting*, *stopping*, hingga proteksi bahaya kelistrikan). Di dunia industri, sistem ini menjadi dasar otomatisasi untuk menggerakkan mesin produksi seperti konveyor, pompa air skala besar, dan kompresor.

### 2. Komponen Utama Rangkaian
* **Saklar (*Push Button*):** Komponen manual untuk menyambung (*Start* - NO) dan memutus (*Stop* - NC) aliran arus listrik sesaat.
* **MCB (*Miniature Circuit Breaker*):** Pengaman utama rangkaian daya dan kontrol dari risiko arus lebih akibat hubung singkat (korsleting).
* **Kontaktor (*Magnetic Contactor*):** Saklar berbasis elektromagnetik yang bertugas menyambung atau memutus arus daya bertegangan tinggi langsung ke beban motor.
* **Relai (*Control Relay*):** Saklar elektromagnetik berarus rendah yang digunakan untuk mengatur logika pada sistem rangkaian kontrol.
* **Overload Relay (TOR):** Komponen proteksi termal untuk mendeteksi panas berlebih akibat beban lebih (*overload*) pada motor dan memutus aliran listrik agar motor tidak terbakar.
* **Timer (*Time Delay Relay*):** Komponen pengatur jeda waktu (*delay*) sebelum mengeksekusi perintah menghidupkan atau mematikan rangkaian.

### 3. Rangkaian Pengunci (*Latching*)
Menggunakan kontak bantu *Normally Open* (NO) pada kontaktor yang dipasang paralel dengan tombol *Start*. Fungsinya adalah membuat jalur aliran listrik alternatif agar koil kontaktor tetap aktif (mengunci) dan motor tetap berputar meskipun tombol *Start* sudah dilepas.

### 4. Rangkaian DOL (*Direct On Line*) Starter
Metode *starting* motor listrik 3 fasa dengan menghubungkannya secara langsung ke tegangan penuh jala-jala. Rangkaian ini dibagi menjadi dua blok utama:
1. **Rangkaian Daya (*Power Circuit*):** Jalur utama 3 fasa (L1, L2, L3) yang mengalirkan daya dari sumber menuju motor melalui kontak utama kontaktor dan *Overload Relay*.
2. **Rangkaian Kontrol (*Control Circuit*):** Jalur 1 fasa berarus kecil yang berfungsi sebagai pengendali operasional koil kontaktor dan lampu indikator.

> **Catatan Aplikasi:** Karena menghasilkan lonjakan arus awal (*inrush current*) yang tinggi (5–7 kali arus nominal), DOL Starter umumnya hanya digunakan untuk motor berkapasitas daya kecil (di bawah 5 kW).

---

## Panduan Simulasi CADe_SIMU

Di dalam repositori ini terdapat skema rangkaian DOL Starter yang disimulasikan menggunakan perangkat lunak **CADe_SIMU** dengan tahapan pengujian sebagai berikut:

1. **Kondisi Standby:** Saat mode simulasi dijalankan dan MCB diaktifkan, arus masuk ke rangkaian kontrol dan menyalakan lampu indikator **OFF** (melalui kontak NC K1).
2. **Kondisi Beroperasi (ON):** Saat tombol **START** ditekan, koil kontaktor **K1** aktif, kontak bantu K1 mengunci (*latching*), motor 3 fasa berputar, lampu OFF padam, dan lampu indikator **ON** menyala.
3. **Kondisi Berhenti (STOP):** Saat tombol **STOP** ditekan, aliran arus ke koil K1 terputus, pengunci terlepas, motor berhenti, dan lampu indikator **OFF** kembali menyala.
4. **Simulasi Gangguan (TRIP):** Saat motor beroperasi dan komponen **OL (Overload)** diaktifkan (simulasi beban lebih), kontak NC 95-96 membuka untuk mematikan motor, sementara kontak NO 97-98 menutup untuk menyalakan lampu indikator **TRIP**.

---

## Perangkat Lunak yang Digunakan
* **CADe_SIMU** (Software CAD Elektroteknik & Simulasi Rangkaian Kontrol)

---

## Informasi Akademik

**Mata Kuliah:** Praktikum Mesin-Mesin Listrik  
**Dosen Pengampu:**
* Rofiq Cahyo Prayogo, S.T., M.T.
* Priyo Sasmoko, S.T., M.Eng.

**Disusun Oleh:**
* **Nama:** Elva Rizqina Khoirun Nisa
* **NIM:** 40040325650031
* **Program Studi:** Teknologi Rekayasa Otomasi
* **Departemen:** Teknologi Industri
* **Fakultas:** Sekolah Vokasi - Universitas Diponegoro

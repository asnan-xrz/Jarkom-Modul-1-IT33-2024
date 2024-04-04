# **LAPORAN RESMI PRAKTIKUM KOMUNIKASI DATA & JARINGAN KOMPUTER MODUL 1**

|Nama                 |NRP               |                                   
|---------------------|----------|
|Agas Ananta Wijaya |5027221004|
---
Berikut adalah Laporan Resmi Praktikum Komunikasi Data & Jaringan Komputer Modul 1 oleh Kelompok IT33.

---

## **TABLE OF CONTENT**

- [creds](#soal1)
- [ATM or ATP or FTP ? 🤔](#soal2)

---

### **creds<a name="soal1"></a>**

>Attacker menyadari jika dia bisa membuat clone ftp server dari target, temukan kredensialn dari server ftp yang dibuat oleh attacker

>nc: 10.15.40.20 10007 

**A. PEMBAHASAN**
1. Di sini saya langsung mencoba follow pada salah satu TCP yang sedikit mencurigakan (mendekati clue).

<img width="1280" alt="1-creds" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/7169cad2-8deb-4b4d-bb75-860458b08034">

  
2. Berdasarkan gambar di bawah ini dapat dilihat bahwa terdapat banyak informasi terkait login akses. Setelah memahami informasi tersebut, dapat disimpulkan bahwa `USER:h3ngk3rTzy` dan `PASS:S!l3ncE`

<img width="1280" alt="2-creds" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/e469882c-d1b4-4f38-afe9-b2bf5c8fc04c">


**B. HASIL**
1. Sehingga didapatkan Flagnya adalah JARKOM2024{s3curE_uR_FtP_I68CPzxjl6FeRrt}

<img width="451" alt="3-creds" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/366ba99e-7391-4d3c-ada5-f589b7ae69c8">


---

### **ATM or ATP or FTP ? 🤔<a name="soal2"></a>**
>Pradityo mencoba mengembangkan server ftp, tetapi seseorang mencoba melakukan bruteforce login, bisakah Anda menganalisis apa yang terjadi?
 
>nc 10.15.40.20 10004

**A. PEMBAHASAN**
1. Untuk mengerjakan soal ini, saya langsung mencoba menggunakan command `strings 'ftp.pcap?token=eyJ1c2VyX2lkIjo2NSwidGVhbV9pZCI6MzcsImZpbGVfaWQiOjZ9.Zg073A.84F_sXaQR9HjBK5x7LfWLcP40oM' | grep "PASS"`
2. Itu adalah perintah strings yang digunakan untuk mengekstrak urutan karakter yang berada dalam file biner dan menampilkannya ke layar.
3. `'ftp.pcap?token=eyJ1c2VyX2lkIjo2NSwidGVhbV9pZCI6MzcsImZpbGVfaWQiOjZ9.Zg073A.84F_sXaQR9HjBK5x7LfWLcP40oM'` adalah nama file yang ingin diperiksa.
4. `| grep "PASS"` akan mencari setiap baris yang mengandung kata "PASS" dalam output yang dihasilkan oleh perintah strings.
5. Sehingga didapatkan output sebagai berikut

<img width="1019" alt="1-ATM" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/0a4713af-8615-49c8-9778-b019463664a6">


6. Hal yang ganjil dari outputnya terletak pada bagian akhirnya. Terdapat pola penulisan Password yang sangat berbeda dari yang lain yaitu `m4y_th3_Kn!fe_ch1p_&_sh4tter`

<img width="439" alt="2-ATM" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/e735882d-0cbf-4bf7-8fc2-68beb1c55275">


**B. HASIL**
1. Sehingga didapatkan Flagnya adalah JARKOM2024{Brut3f0rce_FtP_9h8lPbxHQRkelAq}

<img width="785" alt="3-ATM" src="https://github.com/asnan-xrz/Jarkom-Modul-1-IT33-2024/assets/133721836/d6389352-f32d-4326-957e-45c46c9e4998">


---

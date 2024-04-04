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


  
2. Berdasarkan gambar tersebut dapat dilihat bahwa terdapat banyak informasi terkait login akses. Setelah memahami informasi tersebut, dapat disimpulkan bahwa USER:h3ngk3rTzy dan PASS:S!l3ncE



**B. HASIL**
Sehingga didapatkan Flagnya adalah JARKOM2024{s3curE_uR_FtP_I68CPzxjl6FeRrt}



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



6. Hal yang ganjil dari outputnya terletak pada bagian akhirnya. Terdapat pola penulisan Password yang sangat berbeda dari yang lain yaitu m4y_th3_Kn!fe_ch1p_&_sh4tter




**B. HASIL**
Sehingga didapatkan Flagnya adalah JARKOM2024{Brut3f0rce_FtP_9h8lPbxHQRkelAq}




---

Langkah Setting Dasar MikroTik dengan winbox khusus untuk pemula, lengkap dengan gambar dan script.
Begini Cara Setting MikroTik di RB750, RB750r2, RB750Gr3, RB450G, RB951G, RB941, hAP Lite dan semua type RouterBoard dari awal sampai terhubung ke internet.
Tutorial MikroTik ini bisa di terapkan untuk Hotspot, Warnet, RT RW NET, dan Jaringan lain nya yang skala kecil menengah.
JIka anda baru membeli produk mikrotik dan masih belum mengerti cara konfigurasi MikroTik dari awal…

Berikut ini langkah langkah konfigurasi MikroTik yang perlu anda perhatikan…

# SETTING DASAR MIKROTIK
Secara default semua MikroTik RouterBoard sudah ada konfigurasi yang siap di pakai tanpa harus di setting terlebih dulu.
Tetapi konfigurasi bawaan mikrotik kadang tidak sesuai dengan apa yang sudah direncanakan dari awal.
Sehingga kita perlu melakukan reset terlebih dulu mikrotik RouterOS nya atau bisa juga menghapus setingan standar mikrotik bawaannya.
Berikut urutan seting mikrotik dasar yang perlu anda perhatikan sebagai pembelajaran awal konfigurasi mikrotik.
Netme akan memberikan contoh Langkah Setting MikroTik dasar dengan Modem Indihome, atau dengan ISP lain nya, menggunakan RB750 atau RouterBoard lain nya.

## 1. TOPOLOGI JARINGAN
Langkah pertama yang perlu anda ketahui ialah menentukan Topologi Jaringan sebelum mulai konfigurasi mikrotik.

Buatlah desain topologi jaringan sesuai dengan kondisi dan rencana yang sudah di rencanakan.
<img src="https://drive.google.com/uc?export=view&id=154YOmLOyIGHe4-GexgbFc8XA4WyspQib"/>
Contoh Topologi Jaringan
Keterangan contoh topologi diatas :
<li>MikroTik Port Internet / Ether1 terhubung ke Modem indihome</li>
<li>Mikrotik ether2 terhubung ke HUB untuk dilanjutkan ke beberapa Komputer</li>
<li>MikroTik ether3 terhubung ke Accest Point untuk Wifi</li>
<li>Mikrotik ether4 dan ether5 tidak dipakai</li>

Topologi Jaringan MikroTik gambar di atas ialah hanya contoh, tetapi topologi di atas hampir sama dengan jaringan Warnet, Hotspot, RT RW NET, kantor dan lain sebagainya.

Untuk itu silahkan buat topologi jaringan sesuai dengan kondisi di tempat.
Karena dengan adanya topologi kita jadi mudah untuk seting mikrotik dan trobleshoting jaringan yang akan di bangun.

## 2. IP ADDRESS
IP Address ialah sebuah alamat identitas yang terdiri dari angka biner antara 32 bit sampai 128 bit untuk tiap perangkat host pada jaringan.
Memberi IP address tiap perangkat hukumnya wajib jika ingin terhubung ke internet bahkan terhubung hanya secara lokal.
IP Address sama hal nya seperti alamat rumah yang perlu kita ketahui jika ingin berkunjung atau kirim surat ke alamat rumah tersebut.

Setelah menentukan topologi jaringan mikrotik yang akan dibangun, maka langkah selanjutnya ialah setting IP Address MikroTik agar terhubung ke internet dan MikroTik sebagai gateway pada beberapa komputer dan perangkat lain nya.

Pada gambar di atas, bahwa Internet yang bersumber dari modem ISP hendak di share ke beberapa perangkat dan MikroTik menjadi router sekaligus firewall dan gateway dari semua perangkat yang terhubung.

Berikut cara setting dasar mikrotik pemberian IP address menggunakan Winbox untuk akses ke dalam MikroTik routerOS.

Oh iya….

Pastikan semua perangkat modem, mikrotik, dan komputer sudah di hubungkan sesuai dengan topologi diatas. Dan setingan mikrotik masih default, NetMe anggap masih bawaan atau belum pernah di setting.

Jika belum punya Winbox, silahkan download terlebih dulu.

Buka Winbox dan login MikroTik menggunakan Mac-Address :

Default login mikrotik

<pre>user: admin
password: [tanpa password]</pre>
Login ke MikroTik dengan Mac address
Setelah mac address sudah muncul, klik mac address tersebut dan isi kolom login menggunakan user: admin tanpa password.

Kemudian Klik Connect….

Jika berhasil login maka tampilan MikroTik di winbox seperti berikut :
<img src="https://drive.google.com/uc?export=view&id=14Wf5o_Mv6NncfNOvY5shF4Io-WHVt3RV"/>


<img src="https://drive.google.com/uc?export=view&id=1TYn4m0n87Z6_qcmrOjTRUctwLiONay-C"/>


<img src="https://drive.google.com/uc?export=view&id=1bGCgtkmb6GA1nJpjVHbQ795VX-dx_iY8"/>


<img src="https://drive.google.com/uc?export=view&id=1jh6yJDYRqEn2S4aAPEf7UFt6t4pE8swa"/>


<img src="https://drive.google.com/uc?export=view&id=1zvjp_1WVebVrUSeDuZFA46AUB1m_WZIF"/>


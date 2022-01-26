# LOAD BALANCE METODE PCC
Load balance pada mikrotik adalah ```teknik untuk mendistribusikan beban trafik pada dua atau lebih jalur koneksi secara seimbang, agar trafik dapat berjalan optimal, memaksimalkan throughput, memperkecil waktu tanggap dan menghindari overload pada salah satu jalur koneksi.```
<br>
Selama ini banyak dari kita yang beranggapan salah, bahwa dengan menggunakan loadbalance dua jalur koneksi , maka besar bandwidth yang akan kita dapatkan menjadi dua kali lipat dari bandwidth sebelum menggunakan loadbalance (akumulasi dari kedua bandwidth tersebut). Hal ini perlu kita perjelas dahulu, bahwa loadbalance tidak akan menambah besar bandwidth yang kita peroleh, tetapi hanya bertugas untuk membagi trafik dari kedua bandwidth tersebut agar dapat terpakai secara seimbang.

Dengan artikel ini, kita akan membuktikan bahwa dalam penggunaan loadbalancing tidak seperti rumus matematika 512 + 256 = 768, akan tetapi 512 + 256 = 512 + 256, atau 512 + 256 = 256 + 256 + 256.
Pada artikel ini kami menggunakan RB433UAH dengan kondisi sebagai berikut :
1.    Ether1 dan Ether2 terhubung pada ISP yang berbeda dengan besar bandwdith yang berbeda. ISP1 sebesar 512kbps dan ISP2 sebesar 256kbps.
2.    Kita akan menggunakan web-proxy internal dan menggunakan openDNS.
3.    Mikrotik RouterOS anda menggunakan versi 4.5  karena fitur PCC mulai dikenal pada versi 3.24.

Jika pada kondisi diatas berbeda dengan kondisi jaringan ditempat anda, maka konfigurasi yang akan kita jabarkan disini harus anda sesuaikan dengan konfigurasi untuk jaringan ditempat anda.

## Konfigurasi Dasar

Berikut ini adalah Topologi Jaringan dan IP address yang akan kita gunakan
<center><img src="https://drive.google.com/uc?export=view&id=12sHP2wx86wHIKdJ_IGszkgvZ0bu3oRds"></center>
<pre>/ip address
add address=192.168.101.2/30 interface=ether1
add address=192.168.102.2/30 interface=ether2
add address=10.10.10.1/24 interface=wlan2
/ip dns
set allow-remote-requests=yes primary-dns=208.67.222.222 secondary-dns=208.67.220.220</pre>

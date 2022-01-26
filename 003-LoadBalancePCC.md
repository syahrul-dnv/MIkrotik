# LOAD BALANCE METODE PCC
```Load balance pada mikrotik adalah teknik untuk mendistribusikan beban trafik pada dua atau lebih jalur koneksi secara seimbang, agar trafik dapat berjalan optimal, memaksimalkan throughput, memperkecil waktu tanggap dan menghindari overload pada salah satu jalur koneksi.```
<br>
Selama ini banyak dari kita yang beranggapan salah, bahwa dengan menggunakan loadbalance dua jalur koneksi , maka besar bandwidth yang akan kita dapatkan menjadi dua kali lipat dari bandwidth sebelum menggunakan loadbalance (akumulasi dari kedua bandwidth tersebut). Hal ini perlu kita perjelas dahulu, bahwa loadbalance tidak akan menambah besar bandwidth yang kita peroleh, tetapi hanya bertugas untuk membagi trafik dari kedua bandwidth tersebut agar dapat terpakai secara seimbang.

Dengan artikel ini, kita akan membuktikan bahwa dalam penggunaan loadbalancing tidak seperti rumus matematika 512 + 256 = 768, akan tetapi 512 + 256 = 512 + 256, atau 512 + 256 = 256 + 256 + 256.




# VLAN Management Pada Perangkat Mikrotik
VLAN merupakan suatu fitur yang sangat berguna untuk menghemat resource hardware di jaringan kita. Kita bisa melewatkan beberapa segmen jaringan di 1 interface fisik atau 1 kabel yang sama.
Untuk tutorial penggunaan vlan sudah sering kami bahas pada Youtube Mikrotik Indonesia (Citraweb) dan Artikel Citraweb.
Pada artikel ini kita akan mencoba untuk membuat VLAN management pada perangkat MikroTik. VLAN management adalah suatu VLAN yang bisa kita gunakan untuk melakukan remote ke perangkat.
Jika tanpa menggunakan VLAN management tentunya kita akan merasa kebingungan ketika ingin meremote perangkat / switch yang baru saja kita konfigurasikan vlan.

Konfigurasi VLAN Management pada CRS 3XX Series
Contoh yang pertama kita akan mencoba untuk menggunakan perangkat CRS 3XX Series. Cara ini juga bisa digunakan untuk perangkat router (routerboard / ccr) yang ingin difungsikan sebagai switch.

## Mode Untagged
Untuk mode untagged akan sederhana karena kita akan memberikan IP pada interface bridge nya langsung. Kita tidak akan membuat interface vlan management pada router maupun switch.

Contoh topologi yang kita gunakan adalah seperti gambar berikut:
<img src="https://drive.google.com/uc?export=view&id=1pTIPLUBPkTcjwSdxy1lu7m9dxG_xfHgg">

Konfigurasi pada router, IP Address untuk management terpasang pada interface yang mengarah ke switch.

<img src="https://drive.google.com/uc?export=view&id=1inSLG8n_FubP1YW6B1-M_Pkhi4ABy-aM">
Dan konfigurasi pada switch adalah sebagai berikut:

Pada kasus ini ether1 adalah trunk, ether2, dan ether3 adalah port access yang akan digunakan untuk client.
<img src="https://drive.google.com/uc?export=view&id=1NmZojGhlbZOKJmZV8FgOQmO15OAjrsLv">

Pertama, buat bridge untuk ether1 (trunk), ether2 (access), dan ether3 (access). Jangan lupa tentukan pvid untuk port access, detail cek pada gambar berikut:<br>
<img src="https://drive.google.com/uc?export=view&id=1QWQmI-7FjYC1GUUe5mAu_QZ2yUhohQz7"><br>
<img src="https://drive.google.com/uc?export=view&id=163SwclYa6CWF9MoBgq-s0EMMdnl5QXXZ"><br>
<img src="https://drive.google.com/uc?export=view&id=1HqlbXZBmErJYgNAgzUc6zb5ZmmKnN5An"><br>
<img src="https://drive.google.com/uc?export=view&id=1y1-qKUylP6JIM078-ZWWLTVUHJf3uvBj"><br>

Kemudian konfigurasikan pada tab VLANs<br>
<img src="https://drive.google.com/uc?export=view&id=14kHQ6k6kBXKD90La4iYrP9A8q_N5wwMG">
<br>
<img src="https://drive.google.com/uc?export=view&id=1hHGepMbjDthk5pXkHqrGV82ML19EICi6">

Jangan lupa aktifkan vlan filtering pada bridge yang kita buat tadi.<br>
<img src="https://drive.google.com/uc?export=view&id=1GeDRMde20v1N5OZ3Wm3N5Y4u2MqTrgGI"><br>

Selanjutnya konfigurasikan IP address untuk vlan management pada interface bridge yang sudah dibuat tadi.<br>
<img src="https://drive.google.com/uc?export=view&id=1mDhewmHHJeJhqhirorvEtDp-pFn-1Rb6"><br>

## Mode Tagged
<br>
<img src="https://drive.google.com/uc?export=view&id=1kHCf0KiKdvNxu9gGfQEjIPR7o-WGYxvT">
Dengan menggunakan mode tagged ini kita akan membuat interface vlan untuk vlan management. Sebagai contoh disini akan menggunakan vlan 99 untuk vlan management nya.

Konfigurasi pada router<br>
<img src="https://drive.google.com/uc?export=view&id=1LaMMhmWK8KJEoObWpOg_P1mTthZc_Hbg"><br>

Pada router terdapat interface vlan management yaitu vlan 99 dan IP address terpasang pada interface vlan tersebut.

Konfigurasi pada switch
Untuk topologi nya masih sama, di ether1 sebagai trunk, ether2 dan ether3 sebagai port access.<br>
<img src="https://drive.google.com/uc?export=view&id=1sBlMWcZAnLs6SB63wtmmkHnWkxY87vsP"><br>

<img src="https://drive.google.com/uc?export=view&id=1sBlMWcZAnLs6SB63wtmmkHnWkxY87vsP">


Buat bridge untuk ether1 (trunk), ether2 (access), dan ether3 (access). Jangan lupa tentukan pvid untuk port access, detail cek pada gambar berikut:<br>
<img src="https://drive.google.com/uc?export=view&id=123GoVsQgPfR9DlXiDSWZ3rVFIHl9MarI"><br>
<img src="https://drive.google.com/uc?export=view&id=1SVzM4ywLlOe2bWa3jBNVgylAFjUvKQYb"><br>
<img src="https://drive.google.com/uc?export=view&id=1Bf-C7p-8EDibCeJd7xS6ZGVE8sptJ3bq"><br>

Selanjutnya buat pada tab VLANs untuk vlan 11, vlan 12, dan vlan 99. Untuk VLAN management yaitu vlan 99, tambahkan juga port bridge sebagai tagged.<br>
<img src="https://drive.google.com/uc?export=view&id=1vIDfScQjNvIbiCth4dbFx4j0FagAGLNZ"><br>
<img src="https://drive.google.com/uc?export=view&id=1TfUZHWrNDeoWC6yDAFWmczuO4gDija7P"><br>
<img src="https://drive.google.com/uc?export=view&id=1H8F3ZFgiG7iRGy8O2Nf-J-JH8SVVTEu0"><br>

Setelah itu bisa kita aktifkan untuk vlan filtering nya.<br>
<img src="https://drive.google.com/uc?export=view&id=15bQ1A3n8FWRMVtBD7-Diozao5NPlFcQb"><br>

Kemudian kita bisa membuat interface vlan dengan vlan id 99. Setelah itu bisa diberi IP pada interface vlan99 tersebut sesuai dengan alokasi untuk IP vlan management yang sudah temen temen tentukan sebelumnya. Sampai disini vlan management untuk CRS 3XX Series sudah bisa digunakan.<br>
<img src="https://drive.google.com/uc?export=view&id=10djiK8Tjd4dQQkRb7lLGxqK5VvPiTaTz"><br>

## Konfigurasi VLAN Management pada CRS 1XX / 2XX Series

Untuk konfigurasi VLAN pada CRS 1XX / 2XX Series ini sedikit berbeda. Kita tidak menggunakan menu bridge, namun menggunakan menu switch.

## Mode Untagged

Konfigurasi pada router, IP Address untuk management terpasang pada interface yang mengarah ke switch.<br>
<img src="https://drive.google.com/uc?export=view&id=177g5oKT6DBSR2z25_Mt3ksMnnQ04Q4u9"><br>

Untuk konfigurasi pada switch bisa dilihat pada gambar berikut:<br>
<img src="https://drive.google.com/uc?export=view&id=1xv_hEtFtUDPAmIL3mFu-1A2dMoyNw7wg"><br>
<img src="https://drive.google.com/uc?export=view&id=1Hv3qqaZ0O08n8iMC0pYoXJuqa9k8hwCJ"><br>

Kita buat terlebih dahulu untuk bridge nya, masukkan port ethernet yang menjadi trunk dan access di satu bridge yang sama. Pada contoh ini ether24 adalah trunk, sedangkan ether1 dan ether2 adalah access.
Selanjutnya kita masuk ke menu Switch → VLAN
Tambahkan konfigurasi Ingress VLAN<br>
<img src="https://drive.google.com/uc?export=view&id=1j1xcMfd2uK1hKG8qoXM3d9HqYAKOMgfc"><br>

Tambahkan konfigurasi Egress VLAN<br>
<img src="https://drive.google.com/uc?export=view&id=1VljhT9iez0q0nTpEyfYrm5nsKhG-v2y9"><br>
<img src="https://drive.google.com/uc?export=view&id=1iGGtZNcsEKt_q9o0wXb-38VhIM5Y3vQC"><br>

Konfigurasikan Switch VLAN<br>
<img src="https://drive.google.com/uc?export=view&id=1ZMI-rArdxJTxoXX255A-3QDuixsRc_CI"><br>
<img src="https://drive.google.com/uc?export=view&id=1FcA8laE1qvtnG_XVgPceCiXWgoK6chsC"><br>


Kita tambahkan juga vlan id 0 untuk port ether24 (trunk) dan switch1-cpu.<br>
<img src="https://drive.google.com/uc?export=view&id=1N0-sPQwk-Nbapc3G-GUeAxkjh6KSXhDg"><br>

Konfigurasi pada menu switch → settings dan set untuk Drop If Invalid VLAN On Ports ether24 (trunk), ether1 (access), dan ether2 (access).<br>
<img src="https://drive.google.com/uc?export=view&id=1u0IuVdy8ikGzCi2Je2FJ9xERWoz2rZqy"><br>

Kemudian sudah bisa kita tambahkan IP address untuk interface bridge1 nya.<br>
<img src="https://drive.google.com/uc?export=view&id=1mwE6FGFdMnh4giGGCj-nFdLx9vGCarvO"><br>

## Mode Tagged

<img src="https://drive.google.com/uc?export=view&id=113jN2HwTqo9fcLEjE89TsiCTPBiRrgXC"><br>

Konfigurasi pada router
<img src="https://drive.google.com/uc?export=view&id=105L0mmZYPOc8oM5Qxz1t09lVjklRcL7w"><br>

<!--
<img src="https://drive.google.com/uc?export=view&id="><br>



<img src="https://drive.google.com/uc?export=view&id="><br>

<img src="https://drive.google.com/uc?export=view&id="><br>
<img src="https://drive.google.com/uc?export=view&id="><br>
<img src="https://drive.google.com/uc?export=view&id="><br><img src="https://drive.google.com/uc?export=view&id="><br><img src="https://drive.google.com/uc?export=view&id="><br> -->

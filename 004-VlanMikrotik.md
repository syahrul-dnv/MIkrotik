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
<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">


<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">


<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

<img src="https://drive.google.com/uc?export=view&id=">

# MikroTik RouterOS 
Adalah sistem operasi berbasis kernel Linux. MikroTik RouterOS dapat diinstal pada perangkat keras seri RouterBOARD, atau pada komputer berbasis standar x86, komputer tersebut dijadikan sebagai router jaringan dan menerapkan berbagai fitur tambahan, seperti layanan berbagai jenis firewall, virtual private network (VPN), Administrasi MikroTik RouterOS dapat dilakukan menggunakan perangkat lunak berbasis GUI atau console, berikut adalah perintah dasar MikroTik yang umumnya dijalankan pada console berbasis CLI (Command Line Interface).

## 1. ip address add
Perintah “IP Address Add” di gunakan untuk menambahkan atau mengatur IP Address pada suatu NIC (Network Interface Card), caranya cukup ketikkan perintah “ip address add” kemudian di ikuti dengan IP Address yang akan di set misalnya ” address=10.10.10.1/24″ kemudian di ikuti dengan nama NIC misalnya “interface=ether1”.

<pre>[DosenIT@MikroTik] > ip address add address=10.10.10.1/24 interface=ether1</pre>
Catatan : Anda harus tahu betul nama interface yang IP Address-nya ingin Anda atur, nama interface sebenarnya dapat di ubah dengan perintah tertentu untuk memudahkan pengguna dalam mengenali tiap-tiap port NIC (Network Interface Card), perintah tersebut akan kita bahas di bagian selanjutnya.

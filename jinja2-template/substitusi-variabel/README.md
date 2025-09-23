# PENJELASAN
1. Port Number
{{ port_number }} ini adalah placeholder jinja2.Artinya akan dimasukan nilai variabel yang bernama port_number

2. Server Name
{{ server_name }} Ini juga placeholder yang akan digantikan oleh nilai variabel server_name

* Ansible mengambil file httpd.conf.j2, menemukan {{ port_number }}, dan menggantinya dengan 8080

* Kemudian, Ansible menemukan {{ server_name }} dan menggantinya dengan server-dev.example.com

* File hasil yang sudah terisi lengkap inilah yang di simpan sebagai /etc/apache2/httpd.conf di server target/pod

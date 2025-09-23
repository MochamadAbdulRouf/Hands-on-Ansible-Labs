# PENJELASAN

* {% for server in web_servers %} ini adalah perintah jinja2 untuk memulai perulangan, Artinya setiap item didalam daftar ulangi blok ini.

* server {{ server.ip }}:{{ server.port }}; ini adalah blok yang akan di ulang. disetiap perulangan. {{ server.ip }} akan disini dengan nilai ip dan {{ server.port }} akan disi dengan nilai port.

* {% endfor %} menandakan akhir dari blok perulangan

* Ansible melihat 3 item dalam daftar web_servers. 

* loop 1 : mengambil item pertama ( { ip: '192.168.1.10', port: 80 }) lalu menghasilkan baris server 192.168.1.10:80

* loop 2 dan 3 juga sama saja akan menghasilkan baris server yang sama

* Hasil dari ketiga perulangan ini digabungkan dan menciptakan file konfigurasi akhir.


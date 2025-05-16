<h1>Refleksi</h1>

---

Nama: Makarim Zufar Prambudyo
NPM: 2306241751
Kelas: Advprog-B

---

a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi terbuka standar pada level aplikasi yang dirancang untuk pesan antrian (message queuing). Protokol ini memungkinkan aplikasi yang berbeda untuk berkomunikasi satu sama lain tanpa memperhatikan perbedaan platform atau bahasa pemrograman.

b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what
is the second guest, and what is localhost:5672 is for?
Mengenai format guest:guest@localhost:5672:

Guest pertama: Username untuk koneksi (kredensial login)
Guest kedua: Password untuk koneksi
localhost:5672:

"localhost" adalah nama host yang merujuk ke komputer lokal Anda sendiri
"5672" adalah nomor port default yang digunakan oleh server AMQP (seperti RabbitMQ)


Format ini mirip dengan format URL standar dimana struktur umumnya adalah username:password@host:port. Dalam implementasi RabbitMQ (sistem message broker yang populer menggunakan AMQP), "guest:guest" adalah kredensial default yang disediakan untuk pengujian dan pengembangan lokal.

![slow-connection](/README_image/Screenshot%202025-05-16%20170130.png)
![slow-connection](/README_image/Screenshot%202025-05-16%20171001.png)

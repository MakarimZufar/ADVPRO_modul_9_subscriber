# Refleksi

<h3> Nama: Makarim Zufar Prambudyo</h3>

<h3> NPM: 2306241751 </h3>

<h3> Kelas: Advprog-B </h3>

---

### a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi terbuka standar pada level aplikasi yang dirancang untuk pesan antrian (message queuing). Protokol ini memungkinkan aplikasi yang berbeda untuk berkomunikasi satu sama lain tanpa memperhatikan perbedaan platform atau bahasa pemrograman.

### b. What does it mean? guest:guest@localhost:5672 , what is the first guest, and what
is the second guest, and what is localhost:5672 is for?
Mengenai format guest:guest@localhost:5672:

Guest pertama: Username untuk koneksi (kredensial login)
Guest kedua: Password untuk koneksi
localhost:5672:

"localhost" adalah nama host yang merujuk ke komputer lokal Anda sendiri
"5672" adalah nomor port default yang digunakan oleh server AMQP (seperti RabbitMQ)

Format ini mirip dengan format URL standar dimana struktur umumnya adalah username:password@host:port. Dalam implementasi RabbitMQ (sistem message broker yang populer menggunakan AMQP), "guest:guest" adalah kredensial default yang disediakan untuk pengujian dan pengembangan lokal.

### Simulation Slow Subscriber

![slow-connection](/README_image/Screenshot%202025-05-16%20170130.png)
Pada percobaan ini, saya telah menambahkan delay pada main Publisher sehingga pesan yang dikirimkan tidak sekaligus, melainkan satu persatu dengan jeda waktu. Kemudian, saya menjalankan cargo run pada publisher sebanyak 3 kali.
Hasilnya terlihat bahwa jumlah pesan dalam antrian (Queued messages) cukup tinggi, disebabkan oleh penumpukan pesan saat menjalankan cargo run 3 kali secara berurutan. Pada modul terlihat Queued messages mencapai 20, kemungkinan karena menjalankan cargo run secara sekaligus sebanyak 4 kali sehingga pesan yang menumpuk sebanyak 20 pesan, dengan 5 pesan per eksekusi.

### Running at Least Three Subscribers

![slow-co nnection](/README_image/Screenshot%202025-05-16%20171001.png)
Pada percobaan ini, saya menjalankan tiga subscriber secara bersamaan, dengan cara mengeksekusi perintah cargo run pada publisher sebanyak 4 kali. Setiap eksekusi publisher mengirimkan 5 pesan ke RabbitMQ, sehingga total menghasilkan 20 pesan yang dikirim ke broker.
Yang menarik dari percobaan ini adalah tidak terjadi antrian pesan (message queue) yang terlihat pada RabbitMQ. Ini berarti bahwa setiap pesan yang dikirim oleh publisher langsung diterima dan diproses oleh ketiga subscriber tanpa ada backlog atau antrian pesan yang tertinggal di broker.
Hal ini menunjukkan bahwa RabbitMQ berhasil menyalurkan pesan secara efisien ke ketiga subscriber yang aktif, memungkinkan mereka untuk memproses pesan secara real-time.

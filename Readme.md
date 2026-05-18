### Experiment 2.1
![image](images/exp21.png)
Untuk menjalankan servernya kita perlu menggunakan command 'cargo run --bin server' dan untuk 3 clientnya dengan 'cargo run --bin client' (masing terminal, 1 instance 1 terminal). Yang terjadi ketika kita memasukan teks ke client 1 adalah teks tersebut akan di teruskan oleh server ke client 2 dan 3, tidak terkecuali client 1.

### Experiment 2.2
Untuk mengubah port yang digunakan, kita perlu memodifikasi dua bagian, yaitu server.rs pada bagian TcpListener::bind dan client.rs pada URI koneksi ws://127.0.0.1:8080. Kedua komponen tersebut tetap menggunakan protokol WebSocket yang sama dan harus mengarah ke port yang identik agar koneksi dapat berhasil dilakukan. Setelah kita mengubah konfigurasi server dan client ke port 8080, program tetap dapat berjalan normal tanpa perubahan perilaku.

### Experiment 2.3
Saya menambahkan informasi timestamp ke dalam setiap pesan yang dikirim oleh server. Selain menampilkan IP dan Port dari pengirim, sekarang pesan juga mencakup waktu pengiriman dalam format [HH:MM:SS]. Perubahan ini dapat kita lakukan dengan menambahkan dependency chrono pada Cargo.toml dan memodifikasi server.rs untuk mengekstrak IP dan Port secara terpisah, kemudian memformatnya menjadi "[Timestamp] [IP:Port] Message".

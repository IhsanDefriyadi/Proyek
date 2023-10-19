# proyek - Robot Line Follower

Proyek ini adalah robot yang mengikuti garis. Itu dapat mendeteksi dan mengikuti garis pita di lantai atau arena. Robot menjalankan ROS pada Raspberry Pi, menggunakan Artificial Intelligence (OpenCV) untuk mendeteksi garis, dan Arduino Pro Micro untuk mengontrol kemudi pada robot agar terarah.

Project ini untuk melihat bagaimana ROS dan OpenCV berhasil di terapkan pada robot. Kode OpenCV kemungkinan tidak akan berfungsi di lingkungan pencahayaan yang berbeda. Sistem persepsi tidak dapat digeneralisasi karena bergantung pada garis yang jauh lebih ringan dibandingkan lantai pada arena nya.


Arsitektur Robot 
Arsitektur robot adalah saluran searah. Pertama, data sensor diumpankan dari kamera Raspberry Pi, dan melalui pemrosesan gambar yang melakukan seleksi perspektif dan penyesuaian gambar kontras untuk memfasilitasi deteksi garis.

Setelah gambar diproses, algoritma deteksi garis dijalankan untuk menemukan perkiraan arah garis yang harus diikuti robot. Kode ini menggunakan posisi relatif dan sudut garis untuk menghitung kecepatan dan sudut target yang akan melacak garis.

Data kontrol dikirim melalui koneksi serial ke Arduino Pro Micro, yang menghitung perintah motor individu dan memerintahkan pengontrol motor ganda.

Syarat Penting
Untuk menjalankan proyek ini, Anda harus memiliki setup instalasi ROS Noetic di Raspberry Pi. Repositori ini harus diperiksa ke dalam Catkin. Untuk informasi lebih lanjut, lihat Tutorial ROS .

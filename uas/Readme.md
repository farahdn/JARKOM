Nama: Farah Dina Awalunnisa Sidiq  
NIM: 20220801212  
Mata Kuliah: Jaringan Komputer Lanjut (CIE722)  
Dosen Pengampu: Jefry Sunupurwa Asri, S.Kom., M.Kom.  
Fakultas/Prodi: Ilmu Komputer/Teknik Informatika 

# **Studi Kasus**

Buatlah Topologi dan Konfigurasi ruang lab praktikum Universitas Esa Unggul untuk masing masing kampus (CR, KHI, KJ) bagaimana agar mereka bisa terhubung dan terkoneksi dengan memanfaatkan routing statik, routing dinamik (BGP, RIP, OSPF), Kumpulkan semua ke github masing-masing.

# **Analisis**

Untuk menghubungkan ruang lab di tiga kampus Universitas Esa Unggul (CR, KHI, KJ), setiap kampus memerlukan IP publik yang disediakan oleh ISP agar dapat saling terhubung melalui jaringan internet. ISP, atau Internet Service Provider, adalah penyedia layanan koneksi internet untuk masyarakat luas sehingga memungkinkan akses daring ke dunia digital. Dalam konteks ini, ISP berfungsi sebagai jalur utama untuk menghubungkan ketiga kampus melalui jaringan publik. Selain itu, digunakannya tunnel VPN untuk menciptakan koneksi yang aman antar kampus melalui internet. VPN (Virtual Private Network) tunnel adalah metode dalam jaringan komputer yang menciptakan jalur aman (tunnel) di dalam jaringan publik, seperti internet, guna mengamankan transfer data antara dua atau lebih titik. Jalur ini berfungsi untuk melindungi data sensitif dari ancaman penyadapan atau manipulasi dengan mengenkripsi jalur komunikasi di jaringan publik.

# **Implementasi Tunnel dan ISP Untuk Menghubungkan Tiga Kampus**

**1. Konfigurasi pada Setiap Router**

Langkah pertama adalah mengatur konfigurasi dasar pada setiap router di lokasi KJ, CR, dan KHI. Setiap router dilengkapi dengan dua jenis alamat IP, yaitu IP lokal untuk jaringan internal di lokasi tersebut dan IP publik yang disediakan oleh ISP untuk koneksi internet dan akses antar-lokasi melalui tunnel. Untuk memastikan setiap router mendapatkan IP secara otomatis, fitur DHCP server diaktifkan. Selain itu, Network Address Translation (NAT) digunakan untuk menerjemahkan IP lokal ke IP publik, sehingga perangkat internal dapat mengakses internet dengan aman dan efisien.

**2. Pengaturan Tunnel Antar-Lokasi**

Langkah berikutnya adalah mengonfigurasi tunnel antar-router di ketiga lokasi (KJ, CR, KHI) melalui jaringan ISP. Setiap router membuat tunnel yang diarahkan ke IP publik di lokasi tujuan. Misalnya, router di KJ membangun tunnel menuju IP publik router di CR dan KHI, begitu pula sebaliknya. Dengan konfigurasi ini, jalur komunikasi langsung antar-lokasi dapat dibuat menggunakan ISP sebagai media transportasi, sementara tunnel memberikan keamanan tambahan melalui enkripsi data selama perjalanan.

**3. Routing Statis Untuk Mengatur Jalur Data**

Routing statis digunakan untuk menentukan jalur yang harus dilalui oleh paket data agar mencapai tujuan. Contohnya, untuk mengirim data dari KJ ke CR, router di KJ akan diarahkan ke tunnel menuju IP publik router di CR. Prinsip yang sama berlaku untuk rute ke KHI. Konfigurasi ini memungkinkan perangkat di KJ, CR, dan KHI berkomunikasi langsung tanpa memerlukan pengaturan tambahan pada perangkat lain dalam jaringan lokal.

# **Kesimpulan**
Konfigurasi ini menunjukkan bahwa ISP berperan menyediakan IP publik yang menjadi penghubung antar-lokasi, sedangkan tunnel VPN berfungsi memastikan jalur komunikasi antar-lokasi tetap privat dan aman meskipun menggunakan jaringan publik.
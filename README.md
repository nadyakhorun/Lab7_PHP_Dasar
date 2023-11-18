# Praktikum 7 : PHP Dasar

Nama           : Nadya Khairunnisa

NIM            : 312210133

Kelas          : TI.22.A.1

Mata Kuliah    : Pemrograman Web 1

Dosen Pengampu : Agung Nugroho, S.Kom., M.Kom

# Instruksi Praktikum

1. Pertama persiapkan text editor misalnya VSCode.

2. Kemudian kita buat folder baru dengan nama lab7_php_dasar pada docroot webserver (htdocs).

3. Selanjutnya ikuti langkah-langkah praktikum yang akan dijelaskan berikutnya.

# Langkah-Langkah Praktikum

# 1. Persiapan

Untuk memulai membuat kode php, perlu disiapkan web server dan interpreter PHP terlebih dahulu. Web server yang sering kita gunakan adalah Apache 2 dan interpreter PHP 7. Untuk memudahkan proses praktikum, kita gunakan aplikasi bundle web server yaitu XAMPP.

# 2. Install XAMPP

Unduh XAMPP dari https://www.apachefriends.org/download.html dan pilih versi
portable untuk memudahkan proses installasi. Kemudian extract file tersebut, seusikan
direktorinya (misal: c:\xampp).

![local c](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/4bd1f2ac-d252-42c6-8c74-b9c295677cd6)

# 3. Konfigurasi Web Server

• Konfigurasi Apache

Untuk konfigurasi HTTP server, seperti port yang digunakan akses HTTP, modul
yang diaktifkan, lokasi document root, dll.
Lokasi file: \xampp\apache\conf\httpd.conf

• Konfigrasi PHP

Untuk konfigurasi perilaku engine PHP yang berefek pada keamanan dan performa.
Seperti batas maksimal waktu eksekusi script, batas file yang dapat diupload, error
reporting, dll.
Lokasi file: \xampp\php\php.ini

• Konfigrasi MySql

Konfigurasi server MySQL, seperti administrator user, port, timezone, dll.
Lokasi file: \xampp\mysql\bin\my.ini

# 4. Menjalankan Web Server

Untuk menjalankan Web server dari menu XAMPP Control.

![xampp](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/faefa7c6-ce61-4043-a642-92f1cc5ba639)

• Uji coba apakah server sudah berkerja dengan baik

http://127.0.0.1 atau http://localhost
Tampil halaman utama XAMPP jika server sudah berkerja dengan baik.

• Dokumen Website

Semua file website tempatkan di direktori: \xampp\htdocs\

• Database MySQL

Direktori: \xampp\mysql\
Manajemen database: http://localhost/phpmyadmin

# 5. Memulai PHP

- Buat folder lab7_php_dasar pada root directory web server (c:\xampp\htdocs)

![htdocs](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/b39f8acd-86bc-4fda-af96-6c1f1c964c2b)

- Kemudian untuk mengakses direktory tersebut pada web server dengan mengakses URL:
http://localhost/lab7_php_dasar/

![localhost](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/02a782d5-bfd8-4914-ad93-7ee5b992756e)

# PHP Dasar

- Buat file baru dengan nama php_dasar.php pada directory tersebut. Kemudian buat kode seperti 
berikut.

          <!DOCTYPE html>
          <html lang="en">
          <head>
              <meta charset="UTF-8">
              <title>PHP Dasar</title>
          </head>
          <body>
              <h1>Belajar PHP Dasar</h1>
              <?php
                  echo "Hello World";
              ?>
          </body>
          </html>

- Kemudian untuk mengakses hasilnya melalui URL: http://localhost/lab7_php_dasar/php_dasar.php

![php_dasar](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/bc92b8bd-5020-48dc-ba4c-32927bf524fd)

# Variable PHP

Menambahkan variable pada program

          <?php
          $nim = "0411500400";
          $nama = 'Abdullah';
          echo "NIM : " . $nim . "<br>";
          echo "Nama : $nama";
          ?>

![run variable](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/fe78d7df-652c-4d7f-b129-95306cf63b27)

# Predefine Variable $_GET

          <?php
          echo 'Selamat Datang ' . $_GET['nama'];
          ?>

Untuk mengaksesnya gunakan URL: http://localhost/lab7_php_dasar/latihan2.php?nama=Nadya

![latihan2](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/55e2166d-cf38-493e-b712-fbf141dce525)

# Membuat Form Input

            <!DOCTYPE html>
            <html lang="en">
            <head>
                <meta charset="UTF-8">
                <title>PHP Dasar</title>
            </head>
            <body>
            <h2>Form Input</h2>
            <form method="post">
                <label>Nama: </label>
                <input type="text" name="nama">
                <input type="submit" value="Kirim">
            </form>
            <?php
            echo 'Selamat Datang ' . $_POST['nama'];
            ?>
            </body>
            </html>

![form input](https://github.com/nadyakhorun/Lab7_PHP_Dasar/assets/115801823/2236a3b0-4f29-4649-8657-4b238eb79e56)

# Operator

        <?php
        $gaji = 1000000;
        $pajak = 0.1;
        $thp = $gaji - ($gaji*$pajak);
        echo "Gaji sebelum pajak = Rp. $gaji <br>";
        echo "Gaji yang dibawa pulang = Rp. $thp";
        ?>

# Kondisi IF

        <?php
        $nama_hari = date("l");
        if ($nama_hari == "Sunday") {
            echo "Minggu";
        } elseif ($nama_hari == "Monday") {
            echo "Senin";
        } else {
            echo "Selasa";
        }
        ?>

# Kondisi Switch

        <?php
        $nama_hari = date("l");
        switch ($nama_hari) {
            case "Sunday":
                echo "Minggu";
                break;
            case "Monday":
                echo "Senin";
                break;
            case "Tuesday":
                echo "Selasa";
                break;
            default:
                echo "Sabtu";
        ?>

# Perulangan For

        <?php
        echo "Perulangan 1 sampai 10 <br />";
        for ($i=1; $i<=10; $i++) {
            echo "Perulangan ke: " . $i . '<br />';
        }
        echo "Perulangan Menurun dari 10 ke 1 <br />";
        for ($i=10; $i>=1; $i--) {
            echo "Perulangan ke: " . $i . '<br />';
        }
        ?>

# Perulangan While

        <?php
        echo "Perulangan 1 sampai 10 <br />";
        $i=1;
        while ($i<=10) {
            echo "Perulangan ke: " . $i . '<br />';
            $i++;
        }
        ?>

# Perulangan Dowhile

        <?php
        echo "Perulangan 1 sampai 10 <br />";
        $i=1;
        do {
            echo "Perulangan ke: " . $i . '<br />';
            $i++;
        } while ($i<=10);
        ?>

# Pertanyaan dan Tugas

Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan
nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung
umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang
berbeda-beda sesuai pilihan pekerjaan.

        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>Form Input PHP</title>
        </head>
        <body>
            <h2>Form Input PHP</h2>
            
            <?php
            // Fungsi untuk menghitung umur berdasarkan tanggal lahir
            function hitungUmur($tanggal_lahir) {
                $today = new DateTime();
                $birthdate = new DateTime($tanggal_lahir);
                $umur = $today->diff($birthdate)->y;
                return $umur;
            }
        
            // Fungsi untuk menentukan gaji berdasarkan pekerjaan
            function hitungGaji($pekerjaan) {
                switch ($pekerjaan) {
                    case 'Programmer':
                        return 5000000; // Gaji programmer
                    case 'Desainer':
                        return 4500000; // Gaji desainer
                    case 'Marketing':
                        return 4000000; // Gaji marketing
                    default:
                        return 0; // Pekerjaan tidak valid
                }
            }
        
            // Memproses formulir ketika dikirimkan
            if ($_SERVER["REQUEST_METHOD"] == "POST") {
                $nama = $_POST["nama"];
                $tanggal_lahir = $_POST["tanggal_lahir"];
                $pekerjaan = $_POST["pekerjaan"];
        
                // Validasi input
                if (empty($nama) || empty($tanggal_lahir) || empty($pekerjaan)) {
                    echo "Silakan lengkapi semua field!";
                } else {
                    // Menampilkan output
                    $umur = hitungUmur($tanggal_lahir);
                    $gaji = hitungGaji($pekerjaan);
        
                    echo "<h3>Output:</h3>";
                    echo "Nama: $nama <br>";
                    echo "Tanggal Lahir: $tanggal_lahir <br>";
                    echo "Umur: $umur tahun <br>";
                    echo "Pekerjaan: $pekerjaan <br>";
                    echo "Gaji: Rp. " . number_format($gaji, 0, ",", ".") . "<br>";
                }
            }
            ?>
        
            <!-- Formulir input -->
            <form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]); ?>">
                Nama: <input type="text" name="nama"><br>
                Tanggal Lahir: <input type="date" name="tanggal_lahir"><br>
                Pekerjaan:
                <select name="pekerjaan">
                    <option value="Programmer">Programmer</option>
                    <option value="Desainer">Desainer</option>
                    <option value="Marketing">Marketing</option>
                </select><br>
                <input type="submit" value="Submit">
            </form>
        </body>
        </html>

# Sekian dan Terima Kasih

# Praktik 1

## [Getting Started](https://medium.com/@jonathanmines/the-ultimate-github-collaboration-guide-df816e98fb67).

## Langkah 1: Inisialisasi Proyek Baru

Buka Github dan klik tombol '+' di pojok kanan rop dan pilih 'New Repository'.

![image](https://user-images.githubusercontent.com/70005931/184522111-eeecb8d4-683e-4928-aa43-74dcf6724494.png)

Kemudian isi kolom Repository name dan Description. Tetap publik, dan jangan "Inisialisasi repositori ini dengan README". Jangan mengubah apa pun. Klik "Buat repositori".

![image](https://user-images.githubusercontent.com/70005931/184522149-854d76a0-c456-49eb-9b3f-33706a619959.png)

Selanjutnya Anda akan melihat halaman pengaturan. Ini adalah petunjuk untuk menghubungkan Repo yang baru saja Anda buat di Github (Remote) ke direktori yang Anda buat di terminal Anda (Lokal).

Tulis perintah yang ada di gambar yang ada di sebelah kiri secara satu per satu ke dalam git bash dimulai dengan "echo..." ke terminal saat Anda sedang memasukkan cd ke direktori yang baru saja Anda buat secara lokal.

![image](https://user-images.githubusercontent.com/70005931/184524167-35aa9cd8-1817-4350-bfb3-88c9bf328a1e.png)

Sekarang mari kita perbarui Repo ini. dengan menambahkan sebuah file di dalam folder "github_guide" yang telah anda buat.

![image](https://user-images.githubusercontent.com/70005931/184526794-5546cc25-8cae-4a11-bf87-743be5474e01.png)

Kembali ke terminal Anda dan git add, git commit, dan git Push:

``` bash
$ git add .
$ git commit -m "Second commit"
$ git push
```

![image](https://user-images.githubusercontent.com/70005931/184526807-89fd4b44-011e-4bfc-a397-922eaa0cbf3b.png)

Sekarang periksa repo Anda. dan lihat file yang telah anda tambahkan di dalam folder "github_guide". seharusnya akan terlihat seperti ini

![image](https://user-images.githubusercontent.com/70005931/184527997-fdd62ea4-d968-4361-b1d5-b59c047582ac.png)

Anda telah diinisialisasi dan siap untuk mulai bekerja!!

## Langkah 2: Siapkan Tim Anda

Anda adalah pemain tim, jadi Anda perlu menambahkan tim Anda ke repo agar mereka dapat berkolaborasi. Setelah tim Anda ditambahkan sebagai kolaborator, mereka akan dapat mendorong, menggabungkan, dan banyak hal merusak lainnya, jadi pastikan Anda hanya menambahkan rekan satu tim Anda.

Klik pada tab "Settings" perwakilan Anda, lalu "Collaborators" lalu cari pengguna Github dan tambahkan mereka dengan mengklik "Add Collaborator":

![image](https://user-images.githubusercontent.com/70005931/184528216-0d547a95-8a3c-4ae1-8bcd-689965b50a96.png)

Mereka akan menerima email yang memberitahukan bahwa Anda menambahkan mereka dan akan terdaftar sebagai kolaborator.

![image](https://user-images.githubusercontent.com/70005931/184528343-3d485eba-a5c5-4480-a0dc-b1981a18f056.png)

Anda ingin berkolaborasi di Repo Github yang sama dengan rekan satu tim Anda. Jika Anda seorang kolaborator, buka halaman Github Repo, Git Clone proyek, dan cd ke direktori.

![image](https://user-images.githubusercontent.com/70005931/184528431-62c63d4a-cabc-44ad-bd1e-fbcd89e6f574.png)

``` bash
$ git clone https://github.com/zanmstfa/github_guide.git
$cd github_guide/
```

Dan sekarang Anda siap untuk berkolaborasi!!

## Langkah 3: Berkolaborasi
 
 Saat Anda menggunakan git untuk mengerjakan proyek yang sama dengan banyak orang, ada satu aturan utama yang harus Anda ikuti:

**CABANG UTAMA HARUS SELALU DIPLOYABLE**

Cara agar Master dapat digunakan adalah dengan membuat cabang baru untuk fitur baru dan menggabungkannya ke dalam Master setelah selesai. Inilah cara kerjanya.

### Langkah 3a: Cabang

Untuk memulai, cabang harus selalu mewakili fitur. Misalnya, jika Anda ingin menambahkan kemampuan bagi pengguna untuk masuk, Anda mungkin harus membuat cabang yang disebut "user_authentication" dan di cabang itu Anda hanya perlu memperbarui apa yang Anda perlukan untuk memungkinkan pengguna masuk.

Penting juga saat berkolaborasi agar tim Anda memilih fitur yang tidak memiliki kode yang tumpang tindih. Misalnya, Anda tidak boleh mengerjakan cabang "user_login" pada saat yang sama dengan rekan satu tim Anda bekerja di cabang "user_logout" karena kemungkinan Anda mengerjakan file yang sama dan menulis kode yang tumpang tindih sangat tinggi .

Jadi katakanlah Anda ingin membuat model Pengguna. Di terminal Anda, buat cabang baru:

``` bash
$ git checkout -b create_user
```
“checkout” yang digunakan untuk berpindah antar cabang. Menambahkan "-b" dan nama di akhir membuat cabang baru dan kemudian pindah ke cabang baru itu untuk kita.

Anda bisa melihat apakah kita sudah membuat cabang baru dengan cara

``` bash
$ git branch
```
Yang harus menghasilkan:

![image](https://user-images.githubusercontent.com/70005931/184528667-76af345e-57fa-4991-bb2a-63c9548bb048.png)

Anda sekarang berada di cabang baru dan dapat mulai membuat kode.

Catatan: Sebagai aturan umum, Anda harus sering git add dan git commit ketika Anda menyelesaikan sesuatu yang memungkinkan kode Anda berfungsi (berakhir menjadi beberapa kali dalam satu jam). Misalnya, ketika Anda menyelesaikan suatu metode dan basis kode berfungsi, git commit seperti ini:

``` bash
$ git commit -m "test branch baru"
```

*pastikan sebelumnya anda sudah membuat file terlebih dahulu sebelum **$ git commit** anda bebas membuat file apa saja

``` bash
(use "git add/rm <file>..." to update what will be committed)
```

jika sudah menambahkan sebuah file di dalam branch "create_user" maka anda bisa melakukan **$ git commit**

### Selesai!



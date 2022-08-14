## Praktik 2

# [Team Collaboration With Github](https://code.tutsplus.com/articles/team-collaboration-with-github--net-29876).

[Github](https://github.com/) telah menjadi batu penjuru untuk semua hal perangkat lunak open source. Pengembang menyukainya, berkolaborasi di dalamnya, dan terus-menerus membangun proyek luar biasa melaluinya. Selain menghosting kode kami, daya tarik utama GitHub adalah menggunakannya sebagai alat kolaboratif. Dalam tutorial ini, mari kita jelajahi beberapa fitur GitHub yang paling berguna, terutama untuk bekerja dalam tim, menjadikannya lebih efisien, produktif, dan yang terpenting, menyenangkan!



## Kolaborasi Github dan Perangkat Lunak

> *Satu hal yang menurut saya sangat berguna adalah mengintegrasikan Github Wiki ke dalam proyek kode sumber utama.*


Tutorial ini mengasumsikan bahwa Anda sudah akrab dengan Git, sistem kontrol versi terdistribusi open source, yang dibuat oleh Linus Torvalds pada tahun 2005. Jika Anda memerlukan revisi atau pencarian di Git, kunjungi kursus screencast kami sebelumnya atau bahkan beberapa posting. Selain itu, Anda harus sudah memiliki akun Github dan melakukan beberapa fungsi dasar seperti membuat repositori dan mendorong perubahan ke Github. Jika tidak, buka lebih banyak tutorial sebelumnya tentang itu.


## Alat 1: Menambahkan Anggota Tim
Secara umum ada dua cara menyiapkan Github untuk kolaborasi tim:

1. **Organisasi** : Pemilik organisasi dapat membuat banyak tim dengan tingkat izin yang berbeda untuk berbagai repositori
2. **Kolaborator** : Pemilik repositori dapat menambahkan kolaborator dengan akses Baca + Tulis untuk satu repositor

### Organisasi
Jika Anda mengawasi beberapa tim dan ingin menetapkan tingkat izin yang berbeda untuk setiap tim dengan berbagai anggota dan menambahkan setiap anggota ke repositori yang berbeda, maka Organisasi akan menjadi pilihan terbaik. Setiap akun pengguna Github sudah dapat membuat Organisasi gratis untuk repositori kode sumber terbuka. Untuk membuat Organisasi, cukup telusuri ke halaman pengaturan organisasi Anda:

![organisasi](https://user-images.githubusercontent.com/70005931/184536309-243f6ca6-54a7-4e54-a011-add9eed19182.png)

untuk mengakses halaman tim untuk Organisasi Anda, Anda cukup pergi ke (http://github.com/organizations/[organization-name]/teams), dan untuk melihatnya atau bahkan mengunjungi (https://github.com/organizations/[organization-name]/teams/new), untuk membuat tim baru dengan anggota 3 tingkat izin yang berbeda seperti:

1. **Pull Only**: Ambil dan Gabungkan dengan repositori lain atau salinan lokal.
2. **Push & Pull**: (1) bersamaan dengan pembaruan repo jarak jauh.
3. **Push, Pull & Administrative**: (1), (2) bersama dengan hak atas info penagihan, membuat tim, serta membatalkan akun Organisasi. Baca + Tulis + Akses admin


### Kolaborator
Kolaborator digunakan untuk memberikan akses Baca + Tulis ke satu repositori yang dimiliki oleh akun pribadi. Untuk menambahkan kolaborator, (akun pribadi Github lainnya) cukup buka (https://github.com/[username]/[repo-name]/settings/collaboration)

![kolaborator](https://user-images.githubusercontent.com/70005931/184536917-474c667e-1ba3-4c47-86fb-d9f3e98dda01.png)

Setelah selesai, masing-masing Collaborator akan melihat perubahan status akses pada halaman repositori. Setelah kita memiliki akses Tulis ke repositori, kita dapat melakukan git clone, mengerjakan perubahan, membuat git pull untuk mengambil dan menggabungkan perubahan apa pun di repositori jarak jauh dan akhirnya git push, untuk memperbarui repositori jarak jauh dengan perubahan kita sendiri.

## Alat 2: Pull Request
[Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) adalah cara yang luar biasa untuk berkontribusi ke repositori secara mandiri dengan melakukan forking. Pada akhirnya, jika diinginkan, kami dapat mengirim permintaan tarik ke pemilik repositori untuk menggabungkan perubahan kode kami. Permintaan tarik itu sendiri kemudian dapat memicu diskusi untuk kualitas kode, fitur, atau bahkan strategi umum.

### Memulai Pull Request
Ada dua model permintaan tarik di Github:

1. **Fork & Pull Module**: Digunakan dalam repositori publik yang kami tidak memiliki akses push.
2. **Bagikan Model Repositori**: Digunakan dalam repositori pribadi di mana kami memiliki akses push. Garpu tidak diperlukan dalam kasus ini.

Di sini kita melihat alur kerja antara dua pengguna (pemilik repo dan pemilik repo bercabang) untuk model Fork and Pull:

1. Identifikasi Repositori Github yang ingin Anda sumbangkan, dan klik tombol "Fork" untuk membuat tiruan repositori di akun Github Anda sendiri:

![image](https://user-images.githubusercontent.com/70005931/184537309-8e3c0ef4-da96-418d-b231-9e16c442b5fa.png)
 
2. Ini akan membuat salinan persis dari repositori di akun Anda sendiri.
3. Pilih URL SSH sehingga akan meminta frasa sandi kunci SSH Anda alih-alih nama pengguna dan kata sandi setiap kali Anda git push atau git pull. Selanjutnya, anda akan mengkloning repositori ini ke mesin lokal anda:
```
$ git clone [ssh-url] [folder-name]
$ cd [folder-name]
```
4. Umumnya, kami akan membuat cabang git baru untuk setiap fitur baru. Ini adalah praktik yang baik karena di masa mendatang jika kami memperbarui cabang lebih lanjut setelah beberapa diskusi, permintaan tarik akan diperbarui secara otomatis. Mari buat cabang baru untuk membuat perubahan yang sangat sederhana untuk mengubah file readme.md:
```
$ git checkout -b [new-feature]
```
5. Setelah membuat tambahan yang relevan untuk membangun fitur baru, kami hanya akan melakukan perubahan baru dan checkout ke cabang master git:
```
$ git add .
$ git commit -m "information added in readme"
$ git checkout master
```
6. Pada titik ini, kami akan mendorong cabang ke repositori jarak jauh. Untuk ini pertama-tama kita akan memeriksa nama cabang dengan fitur baru serta alias repositori jarak jauh git. Kemudian kita akan mendorong perubahan menggunakan git Push [git-remote-alias] [branch-name]:
```
$ git branch
* master
readme
$ git remote -v
origin  git@github.com:[forked-repo-owner-username]/[repo-name].git (fetch)
origin  git@github.com:[forked-repo-owner-username]/[repo-name].git (push)
$ git push origin readme
```
7. Di halaman Github repositori bercabang kami, kami akan mengubah ke cabang dengan fitur baru dan kemudian menekan tombol "Tarik Permintaan".





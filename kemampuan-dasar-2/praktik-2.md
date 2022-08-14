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

Setelah selesai, masing-masing Collaborator akan melihat perubahan status akses pada halaman repositori. Setelah kita memiliki akses Tulis ke repositori, kita dapat melakukan git clone, mengerjakan perubahan, membuat git pull untuk mengambil dan menggabungkan perubahan apa pun di repositori jarak jauh dan akhirnya git push, untuk memperbarui repositori jarak jauh dengan perubahan kita sendiri:



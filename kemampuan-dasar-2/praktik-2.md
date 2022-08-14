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

![pull req](https://user-images.githubusercontent.com/70005931/184537663-aaab57f2-05d7-44eb-b371-1c06bd79aa72.png)

8. Setelah mengirimkan permintaan tarik, itu akan langsung membawa kita ke halaman permintaan tarik repositori asli. Kami akan melihat permintaan tarik kami, baik sebagai masalah baru maupun permintaan tarik baru.

9. Setelah diskusi, mungkin pemilik repositori bercabang mungkin ingin menambahkan perubahan pada fitur baru. Dalam hal ini, kami akan checkout ke cabang yang sama di mesin lokal kami, melakukan itu, dan mendorongnya kembali ke Github. Ketika kami mengunjungi halaman permintaan tarik dari repositori asli, itu akan diperbarui secara otomatis!

### Menggabungkan Pull Request
Jika Anda adalah pemilik repositori asli, ada dua cara untuk menggabungkan permintaan tarik yang masuk:

1. Menggabungkan langsung di Github: Jika kita menggabungkan langsung di Github, pastikan tidak ada konflik dan siap untuk digabung ke cabang master. Pemilik repositori asli cukup mengklik tombol hijau "Gabungkan Permintaan Tarik" untuk melakukannya.
2. Penggabungan di mesin lokal kami: Di lain waktu, mungkin ada konflik penggabungan, dan setelah mengklik tombol "info", Github akan memiliki instruksi yang jelas tentang bagaimana kami dapat menggabungkan cabang di mesin lokal kami dengan menarik perubahan dari cabang kontributor.

## Alat 3: Pelacakan Bug
> *Pull Request adalah cara yang luar biasa untuk berkontribusi ke repositori secara mandiri dengan melakukan forking.*

Di Github, pusat untuk semua pelacakan bug adalah Masalah. Meskipun mereka terutama untuk pelacakan bug, juga berguna untuk menggunakan Masalah dengan cara berikut:
1. Bug: Hal-hal yang jelas rusak dan perlu diperbaiki
2. Fitur: Ide-ide baru yang keren dan keren untuk diterapkan.
3. To do list: Daftar periksa item yang harus diselesaikan.

Mari kita jelajahi beberapa fitur dari Issues:
1. Label: Mereka adalah kategori berwarna untuk setiap edisi. Mereka sangat membantu untuk menyaring masalah yang sesuai.
2. Milestones: Mereka adalah kategori tanggal yang dapat dikaitkan dengan setiap masalah dan berguna untuk mengidentifikasi masalah apa yang perlu dikerjakan untuk rilis berikutnya. Juga karena Milestones terhubung ke masalah, secara otomatis memperbarui bilah kemajuan setelah menutup setiap masalah terkait.
3. Pencarian: Pencarian lengkapi otomatis untuk masalah dan pencapaian.
4. Penugasan: Setiap masalah dapat ditugaskan ke orang yang bertanggung jawab untuk memperbaiki masalah tersebut. Ini adalah fitur lain yang berguna untuk melihat apa yang harus kita kerjakan.
5. Tutup otomatis: Komit pesan dengan Perbaikan/Tetap atau Tutup/Tutup/Tutup #[nomor-masalah] akan secara otomatis menutup masalah :
```
$ git add .
$ git commit -m "corrected url. fixes #2"
$ git push origin master
```
6. Sebutan: Siapa pun juga dapat meninggalkan catatan dengan hanya menunjukkan #[nomor-masalah] di pesan mereka. Karena nomor masalah memiliki hyperlink, ini membuatnya sangat mudah untuk menyebutkan masalah terkait selama diskusi.

## Alat 4: Analisis
> *Jelas bahwa kami dapat dengan erat memasangkan daftar tugas kami dan pembaruan untuk komit kode kami.*

Ada dua alat yang memberikan wawasan tentang repositori - Grafik dan Jaringan. Grafik Github memberikan wawasan tentang kolaborator dan komitmen di balik setiap repositori kode, sementara Github Network menyediakan visualisasi pada setiap kontributor dan komitmen mereka di semua repositori bercabang. Analisis dan grafik ini menjadi sangat kuat, terutama saat bekerja dalam tim.

### Grafik

Grafik memberikan analisis terperinci seperti:

1. **Kontributor**: Siapa saja kontributornya? Dan berapa banyak baris kode yang mereka tambahkan atau hapus?
2. **Aktivitas Komit**: Minggu mana komit terjadi dalam setahun terakhir?
3. **Frekuensi Kode**: Berapa banyak baris kode yang dilakukan di seluruh siklus hidup proyek?
4. **Punchcard**: Pada jam berapa biasanya commit dilakukan?

![image](https://user-images.githubusercontent.com/70005931/184542281-87d11fcc-7fc1-4b0c-90c7-fbcc5c367c06.png)

### Jaringan
[Github Network](https://github.blog/2008-04-10-say-hello-to-the-network-graph-visualizer/) adalah alat yang ampuh yang memungkinkan Anda melihat komitmen setiap kontributor dan bagaimana mereka terkait satu sama lain. Ketika kita melihat visualisator secara keseluruhan, kita melihat setiap komit pada setiap cabang dari setiap repositori yang dimiliki jaringan. Wawasan!

![image](https://user-images.githubusercontent.com/70005931/184542359-2b182d77-2ddc-4f92-841a-c81e420f7d72.png)

## Alat 5: Manajemen Proyek
Sementara Masalah Github memiliki kemampuan manajemen proyek dengan Masalah dan Tonggak, beberapa tim mungkin lebih memilih alat lain karena fitur lain atau alur kerja yang ada. Di bagian ini, kita akan melihat bagaimana kita dapat menghubungkan Github dengan dua alat manajemen proyek populer lainnya - Trello dan Pivotal Tracker. Dengan kait layanan Github, kami dapat mengotomatiskan tugas pembaruan dengan komitmen, masalah, dan banyak aktivitas lainnya. Otomatisasi ini membantu tidak hanya menghemat waktu, tetapi juga meningkatkan akurasi pembaruan untuk setiap tim pengembangan perangkat lunak.

### Github dan Trello
Trello menyediakan cara sederhana dan visual untuk mengelola tugas. Menggunakan metodologi Pengembangan Perangkat Lunak Agile, kartu Trello dapat meniru Papan Kanban virtual sederhana. Sebagai contoh, kami akan secara otomatis membuat kartu Trello setiap kali Permintaan Tarik dibuat menggunakan Kait Layanan Github. Mari kita pergi melalui langkah-langkah!

1. Buka akun di Trello jika Anda belum memilikinya dan buat Trello Board baru.

![image](https://user-images.githubusercontent.com/70005931/184542474-3b52afd0-37b3-47e9-bb46-acbda449cd7b.png)

2. Buka repositori Github > Pengaturan > Kait Layanan > Trello

3. Dapatkan TOKEN di bawah Instal Notes #1 dengan hyperlink yang disediakan untuk otentikasi.

4. Di bawah Instal Catatan #2, gunakan URL yang diberikan untuk menghasilkan struktur berformat json yang memberi kita id daftar untuk setiap kartu Trello. BOARDID adalah bagian dari URL ketika kami mengunjungi board di https://trello.com/board/[BOARD-NAME]/[BOARDID]. TOKEN dapat dibuat dengan hyperlink yang diberikan di bawah Install Notes #1.

5. kembali ke kait layanan Github, masukkan id daftar dan token. Centang Aktif, Uji Kait, dan kami siap untuk mendapatkan pembaruan otomatis setiap kali ada Permintaan Tarik.
6. Saat berikutnya ada Pull Request, kartu Trello Pull Request akan otomatis memiliki item baru!

### Github dan Pivotal Tracker 
Pivotal Tracker adalah alat manajemen proyek gesit ringan lainnya di mana perencanaan berbasis cerita memungkinkan tim untuk berkolaborasi dengan mudah dengan langsung bereaksi terhadap berbagai perubahan dan kemajuan proyek. Berdasarkan kemajuan tim saat ini, itu juga dapat membuat bagan untuk menganalisis kecepatan tim, iterasi burn-up, rilis burn-down, dll. Dalam contoh singkat ini, kami akan secara otomatis mengirimkan cerita dengan menautkannya ke komit Github!

1. Buat proyek baru di Pivotal Tracker dengan Cerita baru yang perlu disampaikan.

![image](https://user-images.githubusercontent.com/70005931/184543262-2b5f4fd8-5d55-4104-a840-1016ff8062ad.png)

2. Buka Profil > Token API (tepat di bagian bawah). Salin token API yang diberikan.

![image](https://user-images.githubusercontent.com/70005931/184543318-25001744-8554-4a8c-a75b-482e4d012520.png)

3.Kembali ke repositori Github > Pengaturan > Kait Layanan > Pelacak Penting. Tempel token, centang Aktif dan klik Perbarui Pengaturan. Kami siap untuk mengirimkan Cerita Pelacak Penting secara otomatis dengan Github Commits!

4. akhirnya kami akan melakukan perubahan kami dan menambahkan id pelacak ke pesan komit dengan format git commit -m "message [delivers #tracker_id]"
```
$ git add .
$ git commit -m "Github and Pivotal Tracker hooks implemented [delivers #43903595]"
$ git push
```

5. sekarang, ketika kita kembali ke Pivotal Tracker, kita akan melihat bahwa cerita telah dikirimkan secara otomatis dengan tautan ke komit Github persis yang menunjukkan perubahan file!

Dengan contoh Trello dan Pivotal Tracker ini, jelas bahwa kita dapat memasangkan daftar tugas dan pembaruan dengan komit kode kita dengan erat. Ini adalah penghemat waktu yang luar biasa saat bekerja dalam tim, dan ini meningkatkan akurasi saat menautkan tugas ke komitmen yang tepat. Kabar baiknya adalah, jika Anda sudah menggunakan alat manajemen proyek lain seperti Asana, Basecamp, dan lainnya, Anda juga dapat membuat Service Hooks dengan cara serupa. Jika tidak ada Kait Layanan untuk alat manajemen proyek Anda saat ini, Anda bahkan dapat membuatnya!




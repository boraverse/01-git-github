# Laporan praktikum mata kuliah MDPL
Tulisan ini dibuat untuk memenuhi tugas dari mata kuliah MPDL praktik pertemuan pertama tentang Git & GitHub

## Langkah-langkah Instalasi Git
Sebelum menginstal Git pastikan sudah ada editor text yang terinstal. Git dapat didownload melalui [website resmi Git](https://git-scm.com/).

 1. Setelah proses download selesai,  buka file tersebut. Selanjutnya klik **Next**.
 2. Setelah itu tentukan lokasi untuk instalasi Git. Bisa tetap menggunakan lokasi default.
 3. Pada bagian pilih komponen yang ingin diinstal dibiarkan sesuai default saja. Tidak perlu diubah-ubah.
 4. Shortcut untuk menu Start bisa menggunakan defaultnya bisa juga diganti sesuai keinginan.
 5. Untuk editor teks sesuaikan dengan yang sudah terinstal atau yang biasa digunakan.
 6. Untuk akses Git, pilih **Use Git from the Windows Command Promp**.
 7. Pilih opsi **Use the OpenSSL Library**.
 8. Pilih **Checkout Windows-style, commit Unix_style line endings**.
 9. Pilih **Use MinTTY (the default terminal of MSYS2)**.
 10. Untuk pilihan ini centang dua pilihan lainnya kecuali Enable symbolic links.
 11. Tunggu proses instalasinya selesai. Jika sudah selesai klik **Finish**.
 12. Setelah itu coba jalankan Git Bash atau command prompt dan ketikan **--git version** untuk memeriksa keberhasilan instalasi. Jika berhasil maka akan muncul versi Git yang diinstal.

# Mengelola Repo di account sendiri

## Clone Repo
Proses ini adalah untuk menduplikasi repo yang ada di GitHub ke komputer lokal dengan menggunakan perintah

```bash
$ git clone https://github.com/boraverse/01-git-github
```
Setelah selesai maka di komputer lokal akan ada direktori **01-git-github** seperti yang ada di GitHub. Direktori pada komputer lokal disebut dengan **repo lokal**. Semua perubahan akan dilakukan di komputer lokal dan perubahan tersebut akan tersimpan di dalam **branch** utama repo lokal. Hasil perubahan di komputer lokal akan di-**push** remote repo di GitHub.

## Mengubah isi
Mengubah isi file bisa dilakukan tanpa **branch & merge** bisa juga menggunakan keduanya.

### Tanpa Branch & Merge
Proses ini dilakukan di main **branch**. Jadi file yang sudah diubah isinya akan lansung di **add** menggunakan perintah `$ git add nama_file`. Setelah di-**add** selajutnya harus di-**commit** dengan perintah `$ git commit -m "pesan_commit"`, lalu di-**push** ke remote repo di GitHub dengan perintah `$ git push origin main`.

### Branch & Merge
Sebelum mengubah file haruslah membuat **branch** terlebih dulu yang nanti akan menampung perubahan yang dibuat. Setelah mengalami perubahan maka **branch**-lah yang akan dikirim ke repo di GitHub bukan **branch** utama. *Branch** yang dikirim ke GitHub akan di gabungkan atau **merge** ke **main** (branch utama).


## Sinkronisasi
Terdapat perintah **git pull**, perintah ini digunakan jika akan mengambil commit dari repo remote ke repo lokal dan menggabungkannya.

## Membatalkan Perubahan
Sebelum melakukan perubahan apapun pada sebuah file sebaiknya dibuat dahulu **branch**. Perubahan akan dilakukan pada **branch** baru bukan pada **branch** utama untuk menghindari jika adanya kesalahan pada perubahan yan dilakukan, maka bisa kembali ke **branch** utama dimana belum ada perubahan apapun.
Contoh untuk membuat **branch**

```bash
$ git checkout -b edit-praktik-2
Switched to a new branch 'edit-praktik-2'
```
Untuk mengetahu **branch** mana yang sedang aktif

```bash
$ git branch
* edit-praktik-2
  main
```
Yang memiliki tanda bintang di depannya menandakan **branch** aktif. **git checkout** juga digunakan untuk berpindah **branch**.

Untuk menghapus sebuah **branch** yang tidak dipakai bisa menggunakan perintah 

```bash
$ git branch -d edit-praktik-2
Deleted branch edit-praktik-2 (was c98264f).
```

Perintah **git reset** digunakan untuk meng-undo perubahan yang sudah di-**commit**.

## Undo Commit Terakhir
Terdapat perintah **git revert** yang digunakan untuk mengembalikan file yang sudah terlajur di-**push** ke repo tanpa menghapus history commit. Untuk menggunakannya bisa dengan perintah 

```bash
$ git revert HEAD
```

Perubahan dilakukan secara manual menggunakan editor teks. Setelah selesai maka dapat di-**push** ke repo.

# Mengelola Repo untuk organisasi
# Dasar git

## Misi
1. Membuat repository di github
2. Bagaimana mendapat dan mengirim file ke github
3. Mengambil 'snapshots' pada kode.

## Prasyarat
### cek versi git
```
git --version
```

### ubah lokal branch ke main
```
git config --global init.defaultBranch main
```

## Membuat repository di github
1. Pergi ke profil, klik tmbol '+' di pojok kanan atas
2. buat nama repository misalnya "git_test"
3. ceklis 'add a README file'
4. create repository
5. akan ke redirect ke halaman repo, lalu pilih code, dan pilih SSH.
6. clone:
```
git clone git@github.com:{username}/{repo}.git
```
7. cd {repo}
8. git remote -v untuk mengecek url remote

## Menggunakan git workflow
1. buat file
2. git status dan lihat bahwa nama file berwarna merah yang artinya file belum terlacak.
3. git add {nama file} untuk melacaknya. ketik git status lagi dan file akan berwarna hijau yang berarti sudah terlacak.
4. git commit -m "pesan commit" untuk memberi pesan perubahan pada repo.
5. git log untuk melihat log

## memodifikasi sebuah file atau lebih
1. buka README.md dan test_file.txt dan edit sesuka hati.
2. git add . untuk membahkan pelacakan semua file yang berubah pada folder saat ini.
3. git commit -m "pesan"

## Push local repo ke github
1. git status dan pastikan "nothing to commit, working tree clean"
2. git push atau yang lebih spesifik branch mana: git push origin main
3. cek repo di github.
# setting git
## Install Git
### update system Linux
```
sudo apt update && sudo apt upgrade # turunan debian
sudo pacman -Syu # turunan arch
```

### install git
```
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
```

### check git version
```
git --version
```

## Konfigurasi Git dan Github

### membuat akun github
Daftar di [Github](https://github.com)

### Setup Git
```
git config --global user.name "Your Name"
git config --global user.email "yourname@example.com"
```

### mengubah nama branch utama "master" menjadi "main" (opsional)
```
git config --global init.defaultBranch main
```

### mengubah warna output git (opsional)
```
git config --global color.ui auto
```

### mengaktifkan atau menonaktifkan rebase
Jika dinonaktifkan akan mempermudah dalam kolaboratif karena dapat menggabungkan commit perubahan
dari kedua sumber, yaitu lokal ataupun jarak jauh saat git pull
```
git config --global pull.rebase false
```

### verifikasi
```
git config --get user.name
git config --get user.email
```

## Membuat SSH key
cek apakah SSH key Ed25519 sudah terinstall atau belum
```
ls ~/.ssh/id_ed25519.pub
```
Jika ada keterangan "No such file or directory" artinya belum terinstall.
### SSH key
```
ssh-keygen -t ed25519 -C <youremail>
```
Jika ada prompt, tekan enter atau kosongkan saja.

## Menghubungkan SSH key dengan Github
Gunanya untuk menghubungkan github dengan perangkat tanpa perlu otentikasi email dan password.
1. pergi ke profil github
2. pergi ke settings.
3. Pada tab kiri, pilih SSH and GPG keys
4. New SSH key
5. cat ~/.ssh/id_ed25519.pub
6. copy lalu paste di settings github bagian key pada authentication key
7. [verifikasi](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection):
```
ssh -T git@github.com
# Hi {username}! You've successfully authenticated, but GitHub does not provide shell access.
```

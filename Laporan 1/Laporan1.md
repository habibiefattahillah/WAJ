# Laporan Minggu 2

# Identifikasi Kernel

Kernel adalah komponen fundamental dari suatu Operating System (OS) yang beroperasi sebagai penghubung antara aplikasi software dan komponen hardware komputer. Kernel bertanggung jawab untuk mengatur sumber daya sistem seperti CPU, Memory, I/O Devices, dan Network Connection dan memberikan akses low level ke bagian lain dari OS seperti system services dan aplikasi user, juga menjaga keamanan sistem dengan mengatur akun user dan permissions.  
[![uname -a](https://i.postimg.cc/YSwwzTG8/image-2023-03-09-001419983.png)](https://postimg.cc/jDv9sghJ)Terlihat versi kernel 5.10.0-8-amd64

# Identifikasi Struktur Direktori

[![root folder](https://i.postimg.cc/nr8HNMCb/image-2023-03-09-001823815.png)](https://postimg.cc/FdZ5LryD)

1. /bin: Berisi file executable yang dibutuhkan untuk menjalankan sistem; ls, rm, mkdir, etc.
2. /boot: Berisi sistem kernel dan file-file yang berkait sistem boot.
3. /dev: Berisi file perangkat seperti mouse, keyboard, etc.
4. /lib: Berisi pustaka untuk program yang terinstal di sistem.
5. /sbin: Berisi file executable untuk administrator sistem.
6. /tmp Berisi file sementara
7. /usr: Berisi file dan direktori umum; Program, library, header file, etc.
8. /var: Berisi file yg sering berubah; log sistem, file cache, etc.

# Perbedaan 'su' dan 'sudo'

## **`su`**

Singkatan dari **"switchuser"** atau **"superuser"** yang memperbolehkan user untuk secara sementara menggunakan identitas user lain atau menjadi superuser apabila tidak diinputkan user.

Penggunaan `su` dapat digunakan dengan `su` atau dengan `su -`.
[![su command](https://i.postimg.cc/kG9xqJpz/image-2023-03-09-003826630.png)](https://postimg.cc/7GsCNkDn)

- `su`: Saat berganti user, menyimpan environment variables dan settings dari user asli.
- `su -`: Menggunakan environment variables dan settings dari user target, juga langsung diarahkan ke home directory user target.

## **`sudo`**

Kepanjangan dari **"superuser do"**. Memperolehkan user untuk menjalankan command dengan administrative priviledge tanpa harus switch ke superuser.

Menggunakan "sudo" lebih aman daripada menggunakan superuser karena system administrator dapat mengatur siapa yang dapat menggunakan sudo dan akan menyimpan record command-command yang digunakan dan oleh siapa.

Untuk demonstrasi, dibuat user baru "test1" dengan command `adduser username` di superuser.
[![adduser](https://i.postimg.cc/N0CJszqB/image-2023-03-09-004825621.png)](https://postimg.cc/Z93Fjj5M)

lalu menggunakan command `usermod -aG sudo username` untuk memasukkan user ke grup sudo.
[![sudo test](https://i.postimg.cc/DwyR7sJQ/image-2023-03-09-005206538.png)](https://postimg.cc/tYwB5sz7)  
Dapat dilihat, ketika user "test1" ingin menjalankan command `apt install ssh`, akan muncul error "Permission denied". Kemudian dijalankan command yang sama dengan tambahan sudo di awal, dapatlah dijalankan command tersebut.

# Identifikasi Jenis Repository

[![cat /etc/apt/sources.list](https://i.postimg.cc/xdGsH1zj/image.png)](https://postimg.cc/4KdbRZPj)  
?

# Identifikasi Perintah apt

`apt --help`
[![apt --help](https://i.postimg.cc/dVyrkNyJ/image-2023-03-09-005518896.png)](https://postimg.cc/yD7k2PjG)
apt adalah commandline package manager yang menyediakan command-command untuk mencari dan mengatur paket.

Perintah paling sering digunakan:

- list: Daftar paket berdasarkan nama paket
- search: Mecari di deskripsi paket
- show: Menunjukkan detail paket
- install: Install paket
- reinstall: Menginstall ulang paket
- remove: Menghapus paket
- autoremove: Menghapus paket yang tidak digunakan secara otomatis
- update: Memperbarui paket
- upgrade: Me-upgrade sistem dengan menghapus, menginstall, atau memperbarui paket.
- full-upgrade: Me-upgrade sistem dengan menghapus, menginstall, atau memperbarui paket.
- edit-sources: Mengubah file sumber informasi
- satisfy: Memenuhi dependency

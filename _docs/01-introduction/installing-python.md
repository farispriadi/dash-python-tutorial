---
title: Installing Python
category: Introduction
order: 1
---

## Instalasi di Linux

Dalam buku ini, instalasi Python 3.9 akan kita lakukan pada sistem operasi Ubuntu 20.04. Ada dua cara instalasi, yaitu dengan menggunakan **apt** dan dari *source code*. Anda bebas memilih untuk menggunaan cara yang mana saja.

### Instalasi dengan Apt

1. Update daftar paket ubuntu dan instal beberapa paket yang dibutuhkan.

```bash

$ sudo apt update
farispriadi@ubuntu:~$ sudo apt install software-properties-common

```

2. Menambahkan repository di _sources.list_. 

```bash

farispriadi@ubuntu:~$ sudo add-apt-repository ppa:deadsnakes/ppa

```

3. instal Python3.9 dengan perintah di bawah.

```bash

farispriadi@ubuntu:~$ sudo apt install python3.9

```

4. Cek Python3.9 sudah terpasang di Ubuntu.

```bash

farispriadi@ubuntu:~$ python3.9 --version

Python 3.9.15

```

### Instalasi dengan Source Code

1. Update daftar paket dan install beberapa kebutuhan paket sebelum instalasi Python3.9

```bash

farispriadi@ubuntu:~$ sudo apt-get update
farispriadi@ubuntu:~$ sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev libsqlite3-dev wget libbz2-dev

```

2. Unduh source code Python3.9 

```bash

farispriadi@ubuntu:~$ wget https://www.python.org/ftp/python/3.9.15/Python-3.9.15.tgz

```

3. Ekstrak file source code Python-3.9.15.tgz

```bash

farispriadi@ubuntu:~$ tar -xfV Python-3.9.15.tgz

```

4. Setelah proses ekstrak selesai, pindahkan ke direktori Python-3.9.15 dan jalankan skrip _configure_ untuk melakukan pengecekan kebutuhan paket yang diperlukan.

```bash

farispriadi@ubuntu:~$ cd Python-3.9.15
farispriadi@ubuntu:~/Python-3.9.15$ ./configure --enable-optimizations

```

5. Mulai proses _build_

```bash

farispriadi@ubuntu:~/Python-3.9.15$ make

```

6. Setelah prose _build_ selesai, lakukan instalasi Python3.9 dengan perintah di bawah.

```bash

farispriadi@ubuntu:~/Python-3.9.15$ sudo make altinstall

```
Gunakan _altinstall_ daripada _install_ pada perintah di atas. Opsi _altinstal_ memastikan instalasi Python bawaan dari Ubuntu 20.04 tidak akan ditimpa dengan versi Python yang akan kita instal.

7. Cek Python3.9 sudah terpasang di Ubuntu.

```bash

farispriadi@ubuntu:~/Python-3.9.15$ python3.9 --version

Python 3.9.15

```

8. Setelah memastikan Python3.9 terpasang, hapus direktori Python-3.9.15 dan file Python.3.9.15.tgz.

```bash

farispriadi@ubuntu:~/Python-3.9.15$ cd ..

farispriadi@ubuntu:~$ rm -rf Python-3.9.15*

```

## Instalasi di Windows

1. download

---
title: Installing Virtual Environment
category: Introduction
order: 2
---

## Instalasi Virtual Environment di Linux

Linkungan pengembangan virtual bertujuan untuk mengisolasi paket-paket python menyesuaikan setiap proyek yang kita buat. Untuk membuat lingkungan pengembangan virtual, kita perlu melakukan instalasi _virtual environment_ terutama untuk Python3.9.

1. Untuk menginstalasi _virtual environment_ untuk Python3.9, lakukan dengan perintah di bawah.

``` bash

farispriadi@ubuntu:~$ sudo apt install python3.9-venv

```

2. Setelah terpasang, untuk membuat _virtual environment_ Python3.9 baru, lakukan dengan perintah di bawah.

```bash

farispriadi@ubuntu:~$ python3.9 -m venv python39-venv

```

3. Aktifkan _virtual environment_ untuk menggunakannya.

```bash

farispriadi@ubuntu:~$ source python39-venv/bin/activate
(python39-venv) farispriadi@ubuntu:~$ 

```

4. Test _virtual environment_ dengan mengecek masuk ke mode _Python Shell_.

```bash

(python39-venv) farispriadi@ubuntu:~$ python

Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 

```

5. Tekan __CTRL+Z__ untuk keluar dari _Python Shell_.

```bash

(python39-venv) farispriadi@ubuntu:~$ python
Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 
[2]+  Stopped                 python
(python39-venv) farispriadi@ubuntu:~$ 


```

6. Untuk mematikan _virtual environment_ ketik _deactivate_.

```bash

(python39-venv) farispriadi@ubuntu:~$ deactivate
farispriadi@ubuntu:~$

```

## Instalasi Virtual Environment di Windows
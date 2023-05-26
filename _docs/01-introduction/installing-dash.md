---
title: Installing Dash
category: Introduction
order: 3
---

Untuk melakukan instalasi Dash maupun paket Python lainnya, dalam buku ini kita akan menggunakan package installer for Python atau biasa disebut __pip__. 


1. Pip adalah modul python yang digunakan untuk memanajemen paket-paket python yang akan dipasang, diperbaharui maupun dihapus. Untuk memakai pip kita perlu menginstallnya. Namun dalam _python3.9-venv_ yang telah kita install sudah mencakup pip3.9, sehingga kita tidak perlu melakukan instalasi lagi. Untuk mengecek kita aktifkan kembali _virtual environment_ kemudian ketikkan _pip --version_.

```bash

farispriadi@ubuntu:~$ source python39-venv/bin/activate
(python39-venv) farispriadi@ubuntu:~$ pip --version

pip 22.0.4 from /home/farispriadi/python39-venv/lib/python3.9/site-packages/pip (python 3.9)
```

Keluaran di atas menandakan pip sudah terpasang dengan versi 22.0.4, versi spesifik ini mungkin saja bisa berbeda dengan yang terpasang di komputer Anda. 

2. Setelah pip terpasang kita akan melakukan instalasi Dash. Untuk instalasi dash pada _virtual environment_ lakukan dengan perintah di bawah.

```bash

(python39-venv) farispriadi@ubuntu:~$ pip install dash

```

3. Lakukan pengecekan dengan masuk ke mode _Python Shell_.

```bash

(python39-venv) farispriadi@ubuntu:~$ python
Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import dash
>>> 
```
Tampilan diatas menunjukkan Dash sudah terpasang di _virtual environment_ anda.

Namun jika pada tampilan menunjukkan seperti di bawah ini.

```bash

(python39-venv) farispriadi@ubuntu:~$ python
Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import dash
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'dash'
```
Maka Dash belum terpasang pada _virtual environment_ anda. Solusinya cek koneksi internet dan ulangi __Langkah 2__. 

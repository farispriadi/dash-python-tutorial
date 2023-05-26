---
title: Installing Numpy
category: Introduction
order: 4
---

Numpy adalah pustaka numerik python. Numpy digunakan untuk membuat multidimensional array dan menjalankan operasi matriks yang jauh lebih cepat dibandingkan dengan menggunakan list bawaan Python.

1. Selanjutnya kita akan melakukan instalasi pustaka _numpy_ dengan pip.

```bash

(python39-venv) farispriadi@ubuntu:~$ pip install numpy

```

2. Lakukan pengecekan dengan masuk ke mode _Python Shell_.

```bash

(python39-venv) farispriadi@ubuntu:~$ python
Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import numpy as np 
>>> 
```

3. Membuat array dengan 10 elemen dengan nilai 0
```bash

>>> np.zeros(10)
array([0., 0., 0., 0., 0., 0., 0., 0., 0., 0.])
```

4. Membuat array dengan 10 elemen dengan nilai 1
```bash

>>> np.ones(10)
array([1., 1., 1., 1., 1., 1., 1., 1., 1., 1.])
```

5. Membuat array dengan 10 dengan elemen NaN
```bash

>>> np.full(10,fill_value=np.nan)
array([nan, nan, nan, nan, nan, nan, nan, nan, nan, nan])
```

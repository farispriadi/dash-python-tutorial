---
title: Installing Pandas
category: Introduction
order: 5
---

Pandas adalah pustaka Python untuk data analysis. Pandas digunakan untuk melakukan berbagai macam eksplorasi dan manipulasi data tabular dengan mengubahnya menjadi objek DataFrame.

1. Kita akan menginstalasi _pandas_ menggunakan _pip_. Selain itu kita akan menginstall pustaka **openpyxl** sebagai _engine_ untuk membaca file excel pada _pandas_.

```bash

(python39-venv) farispriadi@ubuntu:~$ pip install openpyxl pandas

```

2. Lakukan pengecekan dengan masuk ke mode _Python Shell_.

```bash

(python39-venv) farispriadi@ubuntu:~$ python
Python 3.9.15 (main, Oct 12 2022, 19:14:24) 
[GCC 9.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import pandas as pd 
>>> 
```

3. Membuat DataFrame baru dari _dict_.

```python

>>> df = pd.DataFrame({'DKI Jakarta':[1,0,np.nan,4],'Jawa Barat': [5,6,np.nan,8],'Jawa Tengah': [9,10,np.nan,12]})
>>> df
	DKI Jakarta  Jawa Barat  Jawa Tengah
0          1.0         5.0          9.0
1          0.0         6.0         10.0
2          NaN         NaN          NaN
3          4.0         8.0         12.0

```

4. Memunculkan jumlah baris dan kolom _DataFrame_
```python
>>> df.shape
(4,3)

```

5. Mengganti nilai _NaN_ dengan angka 0
```python
>>> df = df.fillna(0)
>>> df 
	DKI Jakarta  Jawa Barat  Jawa Tengah
0          1.0         5.0          9.0
1          0.0         6.0         10.0
2          0.0         0.0          0.0
3          4.0         8.0         12.0

```

6. Mengurutkan nilai berdasarkan kolom tertentu

```python
>>> df.sort_values(["Jawa Tengah"])
	DKI Jakarta  Jawa Barat  Jawa Tengah
2          0.0         0.0          0.0
0          1.0         5.0          9.0
1          0.0         6.0         10.0
3          4.0         8.0         12.0
```

7. Menghitung jumlah nilai tiap kolom

```python
>>> df.sum(axis=0)
DKI Jakarta     5.0
Jawa Barat     19.0
Jawa Tengah    31.0
dtype: float64
```

8. Menghitung rata-rata tiap kolom
```python
>>> df.mean(axis=0)
DKI Jakarta    1.25
Jawa Barat     4.75
Jawa Tengah    7.75
dtype: float64
```

9. Menghapus baris pertama (index 0)
```python
>>> df.drop([0],axis=0)
	DKI Jakarta  Jawa Barat  Jawa Tengah
1          0.0         6.0         10.0
2          0.0         0.0          0.0
3          4.0         8.0         12.0
```

10. Menghapus kolom tertentu
```python
>>> df.drop(["Jawa Tengah"],axis=1)
	DKI Jakarta  Jawa Barat
0          1.0         5.0
1          0.0         6.0
2          0.0         0.0
3          4.0         8.0
```

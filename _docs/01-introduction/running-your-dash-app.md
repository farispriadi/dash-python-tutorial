---
title: Running Your Dash App
category: Introduction
order: 6
---



1. Untuk membuat aplikasi pertama, kita akan membuat folder dengan nama __dash-app__ sebagai folder proyek. 

``` bash

farispriadi@ubuntu:~$ mkdir dash-app
farispriadi@ubuntu:~$ cd dash-app
farispriadi@ubuntu:~/dash-app$

```

2. Kemudian kita juga akan membuat ulang _virtual environment_ dalam folder tesebut dan mengaktifkannya.

``` bash

farispriadi@ubuntu:~/dash-app$ python3.9 -m venv python39-venv
farispriadi@ubuntu:~/dash-app$ source python39-venv/bin/activate
(python39-venv) farispriadi@ubuntu:~/dash-app$

```

3. Untuk menulis kode kita akan menggunakan Geany, Anda bisa menggunakan Text Editor atau IDE yang nyaman Anda gunakan seperti VS Code, SublimeText, PyCharm, Atom, Vim, Nano, Gedit dll. Namun pada buku ini kita akan menggunakan text editor __Geany__.

Untuk memasang __Geany__, lakukan dengan perintah di bawah.

```bash

(python39-venv) farispriadi@ubuntu:~/dash-app$ sudo apt install geany

```

Setelah __Geany__ terpasang buat satu file di dalam folder __dash-app__ dengan nama __app.py__. File ini akan dibuka menggunakan __Geany__.

```bash

(python39-venv) farispriadi@ubuntu:~/dash-app$ geany app.py

```

4. Kita akan membuat sebuah aplikasi sederhana, dimana user dapat menginputkan text kemudian text yang telah diinputkan tersebut akan di tampilkan kembali dengan huruf kapital semua. Di bawah ini adalah kode python untuk studi kasus tersebut.

```python

from dash import Dash
from dash import html
from dash import dcc
from dash.dependencies import Input, Output 

app = Dash(__name__)

app.layout = html.Div([
				dcc.Input(placeholder="Masukkan Text",id='input-text'),
				html.Div([],id='output-text')
			])
			

@app.callback(
	Output("output-text","children"),
	[Input("input-text","value")]
)
def update_text(input_text):
	if input_text:
		return f"Anda menulis: {input_text.upper()}"
	else:
		return "Tidak ada yang anda tulis."


if __name__ == "__main__":
	app.run_server(debug=True)


```
Penjelasan dari kode di atas akan diterangkan dalam sub bab berikutnya yaitu __Struktur Aplikasi Dash__.


Simpan kode diatas dengan dalam __app.py__ lalu tutup jendela Geany. Untuk menjalankannya, kita bisa menggunakan langsung pada Geany namun memerlukan konfigurasi binary Python. 

Untuk melakukan konfigurasi binary python pada __Geany__, masuk pada menu __Build > Set Build Commands__ . Pada bagian __Execute commands__ isikan pada baris nomor 1:
 - Pada kolom 2 (lokasi binary python) diisi __python39-venv/bin/python__
 - Pada kolom 3 (Direktori kerja/ folder proyek) diisi __/home/farispriadi/dash-app__

Lalu klik __OK__.

Kemudian klik menu __Build > Execute__ atau dengan shotcut __F5__ untuk menjalankan __app.py__.

Namun agar lebih umum, pada buku ini setiap kali menjalankan kode python langsung melalui terminal. Seperti perintah di bawah.

```bash

(python39-venv) farispriadi@ubuntu:~/dash-app$ python app.py

Dash is running on http://127.0.0.1:8050/

 * Serving Flask app 'test_app' (lazy loading)
 * Environment: development
 * Debug mode: on


```

Aplikasi dapat diakses melalui browser dengan url http://127.0.0.1:8050/.
---
title: Struktur Aplikasi Dash
category: Introduction
order: 7
---


Pada sub bab sebelumnya terdapat kode pada file __app.py__. 


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

Dari kode ini kita akan membedah struktur aplikasi Dash. Struktur Aplikasi Dash dapat dikelompokkan menjadi 6 bagian, antara lain:

1. Import Modul
2. Menginisiasi Aplikasi
3. Membuat Antarmuka
4. Mendefinisikan Update Komponen
5. Menuliskan Fungsi Update
6. Menjalankan Aplikasi


### Import Modul

```python

from dash import Dash
from dash import html
from dash import dcc
from dash.dependencies import Input, Output 

```

Pada bagian **Import Modul** digunakan untuk mendefinisikan modul-modul dari dash yang akan digunakan. Modul minimal untuk membuat aplikasi yang interaktif dengan Dash antara lain Dash, html, dcc, Input dan Output.

Modul Dash (dengan huruf kapital) merupakan kelas dari aplikasi Dash. Modul html merupakan modul untuk memanggil objek-objek yang berkaitan dengan tag HTML, modul yang terkait dengan tata letak. Modul dcc atau kependekan dari _Dash Core Components_ merupakan modul yang menyediakan kemampuan untuk menampilkan objek-objek yang bersifat interaktif seperti Dropdown, Graph, Input Field, Radio Button, Check Box dll.  Input adn Output dari modul dash.dependencies merupakan kelas yang akan digunakan pada dekorator callback untuk kepentingan update value pada tiap komponen.


### Menginisiasi Aplikasi

```python

app = Dash(__name__)

```

Baris kode ini menyatakan inisiasi untuk membuat objek aplikasi Dash. Objek dari Dash akan disimpan dalam variabel dengan nama __app__. 


### Membuat Antarmuka

```python

app.layout = html.Div([
				dcc.Input(placeholder="Masukkan Text",id='input-text'),
				html.Div([],id='output-text')
			])

```

Bagian selanjutnya adalah membuat antar muka yang akan disimpan dalam atribut __layout__ dari objek aplikasi Dash. Untuk membuat antarmuka di awali dengan membuat _Div_ dari modul _html_. Objek Div ini sama fungsinya dengan tag _div_ dalam HTML. Di dalam objek _Div_ terdapat dua objek yang di pisahkan koma, yaitu _dcc.Input_ dan _html.Div_. _dcc.Input_ adalah objek untuk menampilkan tag _Input_ dalam form, objek ini digunakan untuk menginputkan text. Kita lihat di dalam _dcc.Input_ mempunyai _id_ , _id_ akan diguanakan sebagai identitas komponen, _id_ juga dapat diartikan sebagai istilah _id_ dalam CSS. Sedankan _html.Div_ mempunyai _id_ yaitu __output-text__ akan digunakan untuk menampilkan inputan yang dimasukkan dalan objek _dcc.Input_.

### Mendefinisikan Update Komponen

```python

@app.callback(
	Output("output-text","children"),
	[Input("input-text","value")]
)

```

Bagian ini adalah pendefinisian dekorator _callback_ yang digunakan untuk mendefinisikan komponen mana yang akan diupdate dan komponen mana yang menjadi pemicunya. Pemicu diletakkan dalam objek Input sedangkan Target update akan diletakkan dalam objek Output. Argumen yang dimasukkan baik dalam objek Input maupun Output adalah nama _id_ dan atribut komponen yang menjadi masukan atau keluaran.

### Menuliskan Fungsi Update

```python

def update_text(input_text):
	if input_text:
		return f"Anda menulis: {input_text.upper()}"
	else:
		return "Tidak ada yang anda tulis."


```

Bagian ini adalah penulisan fungsi update. Fungsi ini selalu diikuti dengan dekorator _callback_ yang dijelaskan sebelumnya. Jumlah argumen pada fungsi update disesuaikan dengan jumlah _Input_ yang disertakan. Pada contoh ini terdapat satu argumen _input_text_ yang merupakan argumen dari nilai _dcc.Input_.  Fungsi ini akan mengembalikan nilai text yang akan ditampilkan pada atribut _children_, pada objek _html.Div_ dengan _id_-nya _output-text_.

### Menjalankan Aplikasi

```python

if __name__ == "__main__":
	app.run_server(debug=True)


```

Bagian terakhir dari struktur aplikasi Dash adalah _main_. Sama halnya dengan kode Python lainnya statement ini digunakan untuk menjalankan aplikasi utama. Untuk menjalankan aplikasi Dash, dengan memanggil fungsi _run_server pada objek _app_. Dalam fungsi _run_server_ ter dapat keyword _debug_ diisi dengan _True_, mengaktifkan mode debug ketika dalam mode pengembangan.


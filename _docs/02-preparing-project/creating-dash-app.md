---
title: Creating Dash App
category: Preparing Project
order: 2
---


Untuk membuat Dash app kita perlu mengimpor modul Dash yang di perlukan. Kita akan mengimpor kelas _Dash_, modul _html_, dan modul _dcc_ dari modul _dash_. Kelas _Dash_ digunakan untuk membuat objek aplikasi. Modul _html_ digunakan untuk menambahkan tag-tag html , sedangkan  _dcc_ untuk menampilkan fitur interaktif. Baik dan _html_ maupun _dcc_ akan dibahas lebih detail pada **Bab 3 Layout**.


```python
from dash import Dash 
from dash import html
from dash import dcc

app = Dash(__name__)

app.layout = html.Div(["Hello Dash"])

if __name__ == "__main__":
	app.run_server(debug=True)

```


Pada kode di atas objek _Dash_ dibuat dan dimasukkan dalam variable `app`. Baris selanjutnya adalah membuat layout pada aplikasi. Untuk mudahnya ini adalah layout paling minimal untuk dapat menampilkan frasa **Hello Dash**. Layout akan di bahas lebih lanjut di bab selanjutnya.





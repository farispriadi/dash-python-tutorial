---
title: Read XLS File
category: Preparing Project
order: 3
---

Untuk proyek aplikasi ini kita akan menggunakan data berupa file xls. Data tersebut akan kita baca menggunakan pustakan **pandas** dan mengubah nya manjadi objek DataFrame.


```python
from dash import Dash 
from dash import html
from dash import dcc
import pandas as pd 

# Membaca data dari file excel dan diubah menjadi DataFrame
df = read_excel("data/Data_Estimasi_Rt_All.xlsx", engine='openpyxl')

app = Dash(__name__)

app.layout = html.Div(["Hello Dash"])

if __name__ == "__main__":
	app.run_server(debug=True)


```

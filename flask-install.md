# Flask суулгах

## Flask гэж юу вэ?

Flask гэдэг нь Python дээр суурилсан **microframework** юм.

### Хэрэгтэй мэдлэг

* Python хэл дээр ажилдаг байх

### Албан ёсны сайт

* http://flask.pocoo.org

## Flask суулгах

### Бэлтгэл

* **pip** суусан байх шаардлагатай ба доорх линкийн зааврын дагуу суулгана уу
	* [pip суулгах](https://github.com/byam/vagrant/blob/master/pip-install.md)

### Flask суулгах

pip амжилттай суусан бол доорх байдлаар хялбархан суулгана.

```sh
$ sudo pip install Flask
```

Flask амжилттай суугдсаг бол

```sh
$ pip show Flask
---
Name: Flask
Version: 0.10.1
Location: /Library/Python/2.7/site-packages
Requires: Werkzeug, Jinja2, itsdangerous
```

## Flask ажиллуулах

Шинээр **hello.py** гэсэн файл нээж, доорх байдлаар бичэв.

```py
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello():
    return "Hello World!"

if __name__ == "__main__":
    app.run()
```

Доорх байдлаар python командаар framework ажиллах болно.

```sh
$ python hello.py
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
127.0.0.1 - - [20/Mar/2015 12:15:11] "GET / HTTP/1.1" 200 -
```

Дээрхээc http://127.0.0.1:5000/ рүү орвол web brower дээр ``Hello World!`` гэж харагдана.

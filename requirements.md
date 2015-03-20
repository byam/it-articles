# virtualenv орчин доторх package-уудыг хадгалж авах, түүнийгээ өөр орчинд суулгах

## virtualenv орчин доторх package-уудыг хадгалж авах

Одоогийн байгаа TEST-ENV орчин доторх python package-уудыг харах

```sh
(TEST-ENV)$ pip list
aniso8601 (0.92)
Flask (0.10.1)
Flask-RESTful (0.3.2)
Flask-SQLAlchemy (2.0)
itsdangerous (0.24)
Jinja2 (2.7.3)
MarkupSafe (0.23)
pip (6.0.8)
pytz (2014.10)
setuptools (12.0.5)
six (1.9.0)
SQLAlchemy (0.9.9)
Werkzeug (0.10.1)
```

Дээрх package-уудыг **requirements.txt** гэсэн нэрээр хадгалж авах

```sh
# Доорх командаар package-уудын нэр болон version-г хадгалж авна
(TEST-ENV)$ pip freeze > requirements.txt

# requirements.txt-н доторхыг харах
(TEST-ENV)$ cat requirements.txt
aniso8601==0.92
Flask==0.10.1
Flask-RESTful==0.3.2
Flask-SQLAlchemy==2.0
itsdangerous==0.24
Jinja2==2.7.3
MarkupSafe==0.23
pytz==2014.10
six==1.9.0
SQLAlchemy==0.9.9
Werkzeug==0.10.1
```

## Хадгалж авсан package-уудыг шинэ орчинд нэг дор суулгах

**requirements.txt** дотор хадгалж авсан package-уудыг шинэ орчин TEST-NEW-ENV дотор суулгах

```sh
(TEST-NEW-ENV)$ pip install -r requirements.txt
```
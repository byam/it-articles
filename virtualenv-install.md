# virtualenv суулгах, хэрэглэх

## virtualenv гэж юу вэ?

### Товчхондоо

**virtualenv** гэдэг нь **"virtual environment"** гэсэн үгний товчлол ба Python хэл дээр суурилсан ямар нэгэн хөгжүүлэлт(development) хийх үед тухайн прожект бүрт зориулсан хэрэгтэй package-уудыг зохицуулах тусгай хийсвэр орчин юм. 

Жишээ нь A гэсэн прожектэд package-1, package-2 гэсэн 2 package хэрэгтэй бол A прожектэд зөвхөн зориулсан хийсвэр package орчин A-env шинээр үүсгэх юм. A-env орчинд package-1, package-2 суулган A прожектоо ажиллуулана гэсэн үг.

### Албан ёсны сайт

* http://docs.python-guide.org/en/latest/dev/virtualenvs/

## virtualenv суулгах

### Бэлтгэл

* **pip** суусан байх шаардлагатай ба доорх линкийн зааврын дагуу суулгана уу
	* [pip суулгах](https://github.com/byam/it-articles/blob/master/pip-install.md)

### virtualenv суулгах

pip амжилттай суусан бол доорх байдлаар хялбархан суулгана.

```sh
$ sudo pip install virtualenv
```

virtualenv амжилттай суугдсан бол

```sh
$ pip show virtualenv
---
Name: virtualenv
Version: 12.0.7
Location: /Library/Python/2.7/site-packages
Requires:
```

## virtualenv хэрэглээ

### Шинэ package орчин үүсгэх

TEST-ENV гэсэн шинэ package орчин үүсгэх

```sh
$ virtualenv TEST-ENV
New python executable in TEST-ENV/bin/python
Installing setuptools, pip...done.
```

### Үүсгэсэн орчноо идэвхижүүлэх

Дээр үүсгэсэн TEST-ENV гэсэн орчныг идэвхитэй болгох

```sh
# Үүсгэсэн орчны фолдер руу шилжинэ
$ cd TEST-ENV

# Тухайн орчныг идэвхижүүлэх
$ . ./bin/activate
```

Доорх байдлаар тухайн хэрэглэж байгаа package нь ямар орчинд байгааг мэдэж болно.

```sh
# python нь шинэ орчинд анхнаасаа суугдсан байгаа
$ which python
/Users/Bya/TEST-ENV/bin/python			# TEST-ENV орчин доторх python-г ашиглаж байна гэсэн үг

# тухайн орчны python package-үүдийг харах 
$ pip list
pip (6.0.8)
setuptools (12.0.5)		# pip, setuptools нь анхнаасаа шинэ орчинд суугдсан байгаа

```

### Тухайн орчныг идэвхигүй болгох

```sh
# Орчныг идэвхигүй болгох
$ deactivate

# Энэ үед ямар python ашиглаж байгаагааг харвал
$ which python
/usr/bin/python
```



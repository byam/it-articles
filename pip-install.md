# pip суулгах

## pip гэж юу вэ?

**pip** нь Python-ны олон янзын module, package-уудыг суулгахад зориулагдсан tool юм.

## pip суулгах

pip суулгах заавар нь [энд](https://pip.pypa.io/en/latest/index.html) англи хэл дээр дэлгэрэнгүй бичигдсэн байгаа ба энэ хичээл дээр дуурайн хийлээ.

### Бэлтгэл

**Python** суусан байх шаардагатай. Сүүлийн үеийн Mac OS X дээр python сууцан байгаа. Хичээл дээрх python version:

```sh
$ python --version
Python 2.7.6
``` 

### pip суулгах

* [get-pip.py](https://bootstrap.pypa.io/get-pip.py) гэсэн файлыг татаж авна. 
(линк рүү орж бүгдийг нь copy хийн, get-pip.py гэсэн файл үүсгэн дотор нь хадгална.)

* `` $ python get-pip.py `` гэсэн командаар pip суугдах болно.
Амжилттай суусан бол:

```sh
$ pip --version
pip 6.0.8 from /Library/Python/2.7/site-packages (python 2.7)
```

## pip хэрэглээ

### package суулгах

Доорх байдлаар шинэ package суулгана. SomePackage-н оронд суулгах package-аа бичнэ.

```sh
$ pip install SomePackage            # хамгийн сүүлийн version суулгах
$ pip install SomePackage==1.0.4     # тусгай version суулгах
$ pip install 'SomePackage>=1.0.4'     # тусгай version-с бага version суулгах
```
Жишээ болгон **scikit-learn** package суулгав.
 
```sh
$ pip install scikit-learn 
Collecting scikit-learn
  Downloading scikit_learn-0.15.2-cp27-none-macosx_10_6_intel.macosx_10_9_intel.macosx_10_9_x86_64.macosx_10_10_intel.macosx_10_10_x86_64.whl (5.1MB)
    100% |################################| 5.1MB 90kB/s
Installing collected packages: scikit-learn

Successfully installed scikit-learn-0.15.2
```

### Суугдсан package-нд ямар файлууд байгааг харах

Доорх байдлаар суугдсан package-нд ямар файлууд байгааг харна.

```sh
$ pip show --files SomePackage
```


### package устгах

Доорх байдлаар package устгана. SomePackage-н оронд устгах package-аа бичнэ.

```sh
$ pip uninstall SomePackage
```

### Суугдсан package-уудыг харах

Доорх байдлаар суугдсан package-уудыг харна.

```sh
$ pip list
altgraph (0.10.2)
bdist-mpkg (0.5.0)
bonjour-py (0.3)
macholib (1.5.1)
matplotlib (1.3.1)
modulegraph (0.10.4)
numpy (1.8.0rc1)
pip (6.0.8)
py2app (0.7.3)
pyOpenSSL (0.13.1)
pyparsing (2.0.1)
python-dateutil (1.5)
pytz (2013.7)
scikit-learn (0.15.2)
scipy (0.13.0b1)
setuptools (1.1.6)
six (1.4.1)
Twisted (13.2.0)
xattr (0.6.4)
zope.interface (4.1.1)
``` 

### Package хайх

Доор байдлаар package хайна.

```sh
$ pip search SomePackage
```


### package шинэчлэх

```sh
$ pip install --upgrade SomePackage
```

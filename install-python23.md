# Python 2x & Python 3x зэрэг суулгах

## Бэлтгэл

* Mac OS X дээр суулгав
* homebrew ашиглан суулгана.
	* [Mac OS дээр Homebrew суулгах](https://github.com/byam/it-articles/blob/master/brew.md)

2x гэдэг python 2-н хамгийн сүүлийн version гэсэн үг.

## Python 2x & 3x суулгах

### `brew` ашиглан суулгах

```sh
# python 2x суулгах
$ brew install python

# python 3x суулгах
$ brew install python3
```

## Тохиргоо

```sh
# python 2 хаана байгааг шалгах
$ which python
/usr/bin/python

# python 3 хаана байгааг шалгах
$ which python3
/usr/local/bin/python3
```

brew ашиглан суулгаж байгаа тул `/usr/local/bin/` дотор байха ёстой боловч дээрх нь анхнаасаа Mac OS X -д байсан python 2 -г харуулж байгаа гэсэн үг.

Энэ үед `/etc/paths` доторх дарааллыг өөрчлөн, `/usr/local/bin`-н дараа `/usr/bin` бичнэ. 

/etc/paths:

```sh
/usr/local/bin
/usr/bin
/bin
/usr/sbin
/sbin
```

Terminal-аа restart хийсний дараа brew-р суулгасан python 2-г заах болно.

```sh
$ source ~/.zshrc

# python 2 хаана байгааг шалгах
$ which python
/usr/local/bin/python

# python 3 хаана байгааг шалгах
$ which python3
/usr/local/bin/python3
```

## Хэрэглээ

**virtualenv** ашиглан шинэ орчин үүсгэх үедээ **python 3** дээр тохируулмаар байгаа үед доорх байдлаар хийнэ.

* [virtualenv суулгах, хэрэглэх](https://github.com/byam/it-articles/blob/master/virtualenv-install.md)


```sh
# testenv гэсэн шинэ орчинг python 3 дээр үүсгэх
$ virtualenv --python=/usr/local/bin/python3 testenv

# шинэ орчинг идэвхитэй болгох
$ source testenv/bin/activate
(testenv)$ python --version
Python 3.4.3
```


## Ашигласан материал
* http://qiita.com/_rdtr/items/3927e042b2ca18f03b8c
* http://qiita.com/_rdtr/items/22d99c6164af18c7e791
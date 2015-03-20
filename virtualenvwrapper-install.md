# virtualenvwrapper суулгах, хэрэглэх

## virtualenvwrapper гэж юу вэ?

### Товчхондоо

**virtualenvwrapper** нь [virtualenv](https://github.com/byam/it-articles/blob/master/virtualenv-install.md)-н өргөтгөсөн хувилбар бөгөөд package орчнуудтай харьцахад илүү хялбар болсон хувилбар юм. Мөн virtualenvwrapper нь package орчнуудыг нэг дор байрлуулна.

### Албас ёсны сайт

* http://virtualenvwrapper.readthedocs.org/en/latest/index.html

## virtualenvwrapper суулгах

### Бэлтгэл

* **pip** суусан байх шаардлагатай ба доорх линкийн зааврын дагуу суулгана уу
	* [pip суулгах](https://github.com/byam/it-articles/blob/master/pip-install.md)
* **virtualenv** суусан байх шаардлагатай ба доорх линкийн зааврын дагуу суулгана уу
	* [virtualenv суулгах, хэрэглэх](https://github.com/byam/it-articles/blob/master/virtualenv-install.md)


### virtualenvwrapper суулгах
pip, virtualenv амжилттай суусан бол доорх байдлаар хялбархан суулгана.

```sh
# virtualenvwrapper-г pip ашиглан суулгана
$ sudo pip install virtualenvwrapper

# (.bashrc , .zshrc , .profile) гэх startup shell файлдаа доорхыг хуулж нэмж бичнэ
$ vim ~/.zshrc			# zsh ашигладаг тул ~/.zshrc файл дотор vim ашиглан бичив
	export WORKON_HOME=$HOME/.virtualenvs
	export PROJECT_HOME=$HOME/Devel
	source /usr/local/bin/virtualenvwrapper.sh
```
**WORKON_HOME** буюу ``~/.virtualenvs`` дотор шинэ орчнууд хадгалагдах болно.
**PROJECT_HOME** буюу ``~/Devel`` дотор прожект фолдерууд хадгалагдах болно.



virtualenvwrapper амжилттай суугдсан бол

```sh
$ pip show virtualenvwrapper
---
Name: virtualenvwrapper
Version: 4.3.2
Location: /Library/Python/2.7/site-packages
Requires: virtualenv, virtualenv-clone, stevedore
```


## virtualenvwrapper хэрэглээ

### Шинэ орчин үүсгэх

```sh
# TEST-ENV нэр шинэ орчин үүсэх ба автоматаар энэ орчин нь идэвхижих болно.
$ mkvirtualenv TEST-ENV
(TEST-ENV)$

# ~/.virtualenvs дотор шинэ үүсгэсэн TEST-ENV фолдер хадгалагдсан болно
(TEST-ENV)$ ls ~/.virtualenvs
TEST-ENV         postactivate     postmkvirtualenv predeactivate    prermvirtualenv
get_env_details  postdeactivate   postrmvirtualenv premkproject
initialize       postmkproject    preactivate      premkvirtualenv

```

### Package орчингуудыг харах

```sh
# Үүсгэцэн байгаа package орчингуудыг харах
$ workon
TEST-ENV-A
TEST-ENV-B
```
TEST-ENV-A, TEST-ENV-B гэсэн 2 орчин тухайн компьютер дээр байгаа гэсэн үг.

### Орчингууд хооронд шилжих

```sh
# Орчингуудыг харах
$ workon
TEST-ENV-A
TEST-ENV-B

# TEST-ENV-A орчин руу шилжих
$ workon TEST-ENV-A
(TEST-ENV-A)$

# TEST-ENV-A орчинд байхдаа TEST-ENV-B орчин руу шууд шилжих боломжтой
(TEST-ENV-A)$ workon TEST-ENV-B
(TEST-ENV-B)$

```

### Хэрэгтэй коммандууд

```sh
# Project-A-д зөвхөн зориулсан, requirements.txt доторх package-ууд суугдсан A-ENV нэртэй орчин үүсгэх
$ mkvirtualenv -a ~/Project-A/ -r requirements.txt A-ENV
(A-ENV) Project-A $

# Бүх package орчинг харуулах
$ lsvirtualenv

# ENVNAME  нэртэй орчин Устгах
$ rmvirtualenv ENVNAME

# Байгаа package орчныг хуулах
$ cpvirtualenv EXISTING-ENV NEW-ENV
(NEW-ENV)$

# Бүх орчинд зэрэг хандах
$ allvirtualenv pip list

# Идэвхижсэн байгаа package орчны фолдер руу шууд шилжих
$ cdvirtualenv ENV-NAME

# Глобал package-уудыг одоо идэвхитэй байгаа орчинд хэрэглэж болдон болгох
(ENV-NAME)$ toggleglobalsitepackages
Enabled global site-packages
(ENV-NAME)$ toggleglobalsitepackages # идэвхигүй болгох
Disabled global site-packages

# Шинж прожект үүсгэх
$ mkdir ~/Devel
$ mkproject myproj
(myproj)~Devel/myproj $

# Прожект, package орчин 2-г холбох
$ setvirtualenvproject ~/.virtualenvs/ENV-NAME ~/Devel/myproj
Setting project for ENV-NAME to /Users/Bya/Devel/myproj

# Тухайн орчны шинээр суусан бүх package-үүдийг устгах
$ wipeenv

```

### Бусад коммандууд

* Доорх линк дээр коммандууд тайлбартайгаа байгаа
	* http://virtualenvwrapper.readthedocs.org/en/latest/command_ref.html

* мөн ``$ virtualenvwrapper`` гэсэн коммандаар хэрэглэж болох коммандуудыг харж болно.

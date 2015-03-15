#Mac OS дээр Homebrew суулгах

### Homebrew гэж юу вэ?

Хэрэгтэй **package** -ууд болон **программуудыг** хялбархан аргаар суулгадаг Mac OS дээр байдаг **package manager** юм. Linux дээрх **apt-get** тэй адил.

###Homebrew суулгах

```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
###Амжилттай суусан бол

```
$ brew doctor
Your system is ready to brew.
```
###Ашиглагдах коммандууд

```
$ brew help
Example usage:
  brew [info | home | options ] [FORMULA...]
  brew install FORMULA...
  brew uninstall FORMULA...
  brew search [foo]
  brew list [FORMULA...]
  brew update
  brew upgrade [FORMULA...]
  brew pin/unpin [FORMULA...]

Troubleshooting:
  brew doctor
  brew install -vd FORMULA
  brew [--env | config]

Brewing:
  brew create [URL [--no-fetch]]
  brew edit [FORMULA...]
  open https://github.com/Homebrew/homebrew/blob/master/share/doc/homebrew/Formula-Cookbook.md

Further help:
  man brew
  brew home
```

###Хэрэглээ

Жишээ: **wget** суулгах
```bash
$ brew install wget
```

Homebrew ашиглаж суугдсан **package**-ууд **/usr/local** дотор байрлана.
```
$ cd /usr/local
$ ls -l bin
total 16
-rwxr-xr-x  1 Bya  admin  791 Mar 15 13:07 brew
lrwxr-xr-x  1 Bya  admin   30 Mar 15 13:46 wget -> ../Cellar/wget/1.16.3/bin/wget
```

### Ашигласан материалууд
* http://brew.sh



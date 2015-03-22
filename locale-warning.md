# perl: warning: Falling back to the standard locale ("C").

git clone хийх үед доорх сануулга гарч ирэв 

```sh
perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
LANGUAGE = (unset),
LC_ALL = (unset),
LC_CTYPE = "UTF-8",
LANG = "ja_JP.UTF-8"
are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
```

``~/.zshrc`` дотор доорхыг бичихэд сануулга гарч ирэхээ болив

```sh
LC_CTYPE=ja_JP.UTF-8
LC_ALL=ja_JP.UTF-8
```

### Хэрэглэсэн материал
* http://stackoverflow.com/questions/2499794/how-can-i-fix-a-locale-warning-from-perl
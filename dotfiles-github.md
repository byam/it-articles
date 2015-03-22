# dotfiles-г GitHub дээр хадгалах

## dotfiles гэж юу вэ?

dotfiles гэдэг ямар нэгэн software болон package-уудын settings файл юм. 

Жишээ нь:

|package нэр | Setting файл | 
|:-----------|------------:|
| vim       |        .vimrc |
| zsh     |      .zshrc |   
| bash       |        .bashrc |

## dotfiles-г GitHub дээр хадгалах

### dotfiles гэсэн фолдер үүсгэн, түүндээ setting файлуудаа байрлуулна

```sh
# шинэ фолдер үүсгэх
$ mkdir dotfiles

# setting файлуудаа зөөх
$ mv ~/.vimrc dotfiles
$ mv ~/.zshrc dotfiles

```

### symbolic link ашиглах dotfiles доторх setting файлуудыг идэвхижүүлэх

```sh
$ ln -sf ~/dotfiles/.vimrc ~/.vimrc
$ ln -sf ~/dotfiles/.zshrc ~/.zshrc
```
Үүнээс хойш ямар нэг өөрчлөлт оруулахдаа мэдээж ``~/dotfiles/`` доторх setting файлыг өөрчлөнө гэсэн үг.

### GitHub дээр dotfiles фолдерыг тавих

1. Эхлээд https://github.com/new руу орж ``dotfiles`` гэсэн нэртэй repository үүсгэнэ.


2. Үүсгэсэн фолдер руугаа push хийнэ.

```sh
$ cd ~/dotfiles
$ git init
Initialized empty Git repository in /Users/Bya/dotfiles/.git/
$ git add .
$ git commit -m "added .vimrc .zshrc"
$ git remote add -f dotfiles https://github.com/byam/dotfiles.git
$ git push -u origin master 
```

## Ашигласан материал

* http://qiita.com/himinato/items/7f5461814e8ed8916870
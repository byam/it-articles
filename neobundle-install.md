# VIM дээр NeoBundle суулгах

## NeoBundle гэж юу вэ?
NeoBundle нь vim дээр plugin суулгах, устгах зэргийг зохицуулах tool юм.

## Бэлтгэл

NeoBundle суулгахын тулд **git** суусан байх шаардлагатай.

Энэ хичээл дээрх **git** version:

```bash
$ git --version
git version 1.9.5 (Apple Git-50.3)
```

## NeoBundle суулгах

### Neobundle татах
```bash
# .vim фолдер дотор bundle гэсэн фолдер шинээр үүсгэнэ
$ mkdir -p ~/.vim/bundle

# үүсгэсэн bundle фолдерны neobundle.vim татаж авна
$ git clone git://github.com/Shougo/neobundle.vim ~/.vim/bundle/neobundle.vim
```

### Neobundle тохируулга

VIM -н тохируулга файл ```~/.vimrc``` дотор доорх байдлаар бичнэ.

```bash
if has('vim_starting')
	set nocompatible               " Be iMproved
	" Required:
	set runtimepath+=~/.vim/bundle/neobundle.vim/
endif

call neobundle#begin(expand('~/.vim/bundle/'))

NeoBundleFetch 'Shougo/neobundle.vim'

" энд plugin тохируулна
NeoBundle 'суулгах plugin-н нэр'

call neobundle#end()
filetype plugin indent on

NeoBundleCheck

```

##NeoBundle ашиглан vim plugin суулгах

vim-ээр ``~/.vimrc`` файлыг нээж, ``NeoBundle 'суулгахPLUGINнэр' `` гэж бичэн ``:NeoBundleInstall`` гэвэл идэвхижих болно.

**Хэрэгтэй plugin-ууд**
Доорх линкээр орж хэд хэдэн хэрэглэхэд хялбар **vim plugin**-уудыг суулгана уу

* [Хэрэглэхэд хялбар **Vim Plugin**-ууд суулгах](http://qiita.com/jnchito/items/5141b3b01bced9f7f48f)
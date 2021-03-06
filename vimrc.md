# VIM дээрх тохиргоонууд

## vimrc гэж юу вэ?

**vimrc** гэдэг нь **vim**-н тохиргоо хийх файл юм.
Mac OSX дээр ```~/.vimrc``` дээр байрлана. Хэрэв ийм файл байхгүй бол ```mkdir ~/.vimrc``` гэж шинээр үүсгэн тохиргоонуудаа хийх юм.

## Хэрэгтэй хялбар тохиргоонууд

```~/.vimrc``` дотор доорх байдлаар бичнэ.

```bash
" мөрүүдийг дугаартай болгоно
set number

" vim-р нээсэн цонхыг нэртэй болгох
set title

" команд харуулах
set showcmd

" кодуудыг өнгөөр ялгах
syntax on

" үг хайж байх үед, эхний үсэг хийснээс хайлт эхлэх
set insearch

" хаалтны эхлэл төгсгөлийг харуулах
set showmatch

" автоматаар зай авах(индент)
set autoindent

" tab-н уртыг тохируулах
set tabstop=4

" syntax-ны өнгийг тохируулах
colorscheme desert

" мөрний дугаарын өнгийг тохируулах
highlight LineNr ctermfg=darkyellow

" vim дээр mouse ажилдаг болгох
set mouse=a

```

## VIM дээр plugin суулгах

### Бэлтгэл
VIM дээр plugin суулгахын тулд, plugin зохьцуулагч NeoBundle суулгасан байх хэрэгтэй. Доорх линкээр орж суулгана уу.

[VIM дээр NeoBundle суулгах](https://github.com/byam/vagrant/blob/master/neobundle-install.md)

### Хэрэглэхэд хялбар **Vim Plugin**-ууд суулгах
Доорх линкээр орж суулгана уу
* [Хэрэглэхэд хялбар **Vim Plugin**-ууд суулгах](http://qiita.com/jnchito/items/5141b3b01bced9f7f48f)

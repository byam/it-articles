# rbenv суулгах

## rbenv гэж юу вэ?

ruby-н version солих tool юм.

## rbenv суулгах

### Бэлтгэл
* Mac OS X
* `brew` суусан байх. Суугаагүй бол [Mac OS дээр Homebrew суулгах](https://github.com/byam/it-articles/blob/master/brew.md) -ээс үзнэ үү.

### rbenv суулгах

`brew` ашиглан суулгах

```sh
$ brew install rbenv ruby-build

$ echo 'eval "$(rbenv init -)"' >> ~/.zshrc
$ source ~/.zshrc

$ rbenv --version
rbenv 0.4.0
```

## rbenv хэрэглээ

### ruby суулгах

```sh
# ruby ямар version суулгаж болохыг харах
$ rbenv -list
...
2.2.0-rc1
2.2.0
2.2.1
2.3.0-dev
...

# ruby 2.2.1 -г суулгах
$ rbenv install 2.2.1

# суусан эсэхийг харах
$ rbenv versions
* system (set by /Users/Bya/.rbenv/version)
  2.2.1
  
# version 2.2.1-г идэвхжүүлэх
$ rbenv global 2.2.1
$ rbenv versions
  system
* 2.2.1 (set by /Users/Bya/.rbenv/version)
```

### ruby version солих


```sh
# ахин нэг ruby version суулгая
$ rbenv install 1.9.3-p551

# ruby version-гууд
$rbenv versions
  system
  1.9.3-p551
* 2.2.1 (set by /Users/Bya/.rbenv/version)

# version 1.9.3 болгох
$ rbenv global 1.9.3-p551
$ rbenv versions
  system
* 1.9.3-p551 (set by /Users/Bya/.rbenv/version)
  2.2.1
```

### ruby version устгах

```sh
$ rbenv versions
  system
  1.9.3-p551
* 2.2.1 (set by /Users/Bya/.rbenv/version)

$ rbenv uninstall 1.9.3-p551
rbenv: remove /Users/Bya/.rbenv/versions/1.9.3-p551? y

$ rbenv versions
  system
* 2.2.1 (set by /Users/Bya/.rbenv/version)
```

### Тухайн фолдерт ruby version тохируулах

```sh
$ mkdir TEST
$ cd TEST
$ rbenv versions
  system
  1.9.3-p551
* 2.2.1 (set by /Users/Bya/.rbenv/version)

# TEST фолдерт ruby 1.9.3 болгох
$ rbenv local 1.9.3-p551
$ rbenv versions
  system
* 1.9.3-p551 (set by /Users/Bya/TEST/.ruby-version)
  2.2.1

# Бусад фолдер дох ruby version
$ cd
$ rbenv versions
  system
  1.9.3-p551
* 2.2.1 (set by /Users/Bya/.rbenv/version)
```

## Ашигласан материал (References)

* [日本語](http://dev.classmethod.jp/server-side/language/build-ruby-environment-by-rbenv/)
* [English](https://github.com/sstephenson/rbenv#homebrew-on-mac-os-x)
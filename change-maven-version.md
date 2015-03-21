# Change Apache Maven Versions

### Show current maven version

```sh
$ mvn -v
Apache Maven 2.2.1 (r801777; 2009-08-07 04:16:01+0900)
Java version: 1.7.0_75
Java home: /Library/Java/JavaVirtualMachines/jdk1.7.0_75.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x" version: "10.10.2" arch: "x86_64" Family: "mac"
```

### Deactive current version, and install new version 3

```sh
# unlink current version maven2
$ brew unlink maven2
Unlinking /usr/local/Cellar/maven2/2.2.1... 3 symlinks removed

# install maven31
$ brew install maven31
==> Installing maven31 from homebrew/homebrew-versions
==> Downloading http://www.apache.org/dyn/closer.cgi?path=maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.ta
Already downloaded: /Library/Caches/Homebrew/maven31-3.1.1.tar.gz
==> Caveats
WARNING: This older version will conflict with Maven if installed at the
same time.
==> Summary
🍺  /usr/local/Cellar/maven31/3.1.1: 61 files, 6.3M, built in 2 seconds

# show current maven version
$ mvn -v
Apache Maven 3.1.1 (0728685237757ffbf44136acec0402957f723d9a; 2013-09-18 00:22:22+0900)
Maven home: /usr/local/Cellar/maven31/3.1.1/libexec
Java version: 1.7.0_75, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.7.0_75.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.10.2", arch: "x86_64", family: "mac"

```

### Change Apache Maven Versions

```sh
# unlink current maven31
$ brew unlink maven31
Unlinking /usr/local/Cellar/maven31/3.1.1... 4 symlinks removed

# link maven2
$ brew link maven2
Linking /usr/local/Cellar/maven2/2.2.1... 3 symlinks created

# show current version
$ mvn -v
Apache Maven 2.2.1 (r801777; 2009-08-07 04:16:01+0900)
Java version: 1.7.0_75
Java home: /Library/Java/JavaVirtualMachines/jdk1.7.0_75.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x" version: "10.10.2" arch: "x86_64" Family: "mac"

```

### Guide

* [Maven2とMaven3の切り替](http://qiita.com/tksmaru/items/c2342d9894bc30fae65a)

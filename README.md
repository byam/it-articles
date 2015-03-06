#Vagrant

##1. Vagrant гэж юу вэ?
### Товчхондоо
- Virtual machine

### Албан ёсны сайт
-  https://www.vagrantup.com

### Хэрэгтэй мэдлэг
- Unix
- Ruby

### Бэлтгэх хэрэгтэй зүйлс
Доор линкээр орон татаж суулгана
  - [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  - [Vagrant](https://www.vagrantup.com/downloads.html)

Энэ хичээл дээрх version:
```
$ vagrant -v
Vagrant 1.6.2

$ VBoxManage --version
4.3.12r93733
```
##2. Box суулгах
###Box template татах
[Энд](http://www.vagrantbox.es)-ээс татаж суулгах ба энэ удаад MacOS дээр centos 6.4 суулгах

```
$ vagrant box add centos64 https://github.com/2creatives/vagrant-centos/releases/download/v6.4.2/centos64-x86_64-20140116.box
```
Амжилттай татагдсан бол
```
$ vagrant box list
centos64 (virtualbox)
```
###Virtual Machine initialize
Шинэ myCentOSVM гэсэн фолдер үүсгэн түүн дотор initialize хийхэд Vagrantfile гэсэн файл үүсэх болно.
```
$ mkdir myCentOSVM
$ cd myCentOSVM
$ vagrant init centos64
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.
$ ls
Vagrantfile
```
###Virtual Machine  ажиллуулах
Vagrantfile файл байгаа фолдер дотор
```
$ vagrant up

```
Амжилттай суусны дараа VirtualBox дээр доорх байдлаар myCentOSVM running гэж харагдана.

![alt tag](https://raw.github.com/byam/vagrant/master/images/IMAGE-1.png)

##3. Vitual Machine stop・restart・delete

vagrant гэсэн коммандын араас доорх коммандуудыг ашиглана
  - status
  - suspend - resume
  - halt - up   (Унтраас - Асаах)
  - reload

  - destroy   (Устгах)

##4. Virtual Machine-той холбох
###Virtual Machine той холбогдох
```
$ vagrant ssh
Welcome to your Vagrant-built virtual machine.
[vagrant@localhost ~]$ pwd
/home/vagrant
```

web server install
```
[vagrant@localhost ~]$ sudo yum -y install httpd
```

```
sudo service httpd start
sudo chkconfig httpd on
sudo service iptables stop
sudo chkconfig iptables off
```

##5. web хуудас үзэх
###Hello World

```
[vagrant@localhost ~]$ cd /var/www/html
[vagrant@localhost html]$ sudo vi index.html 	#'Hello World' гэж бичэв
[vagrant@localhost html]$ cat index.html
<h1>Hello World!<h1>
[vagrant@localhost html]$
```
###Private Network
Virtual machine-с гаран Vagrantfile-дээр（config.vm.network :private_network, ip: "192.168.33.10"）-г идэвхитэй болгон ахин уншуулна.
```
[vagrant@localhost html]$ exit
logout
Connection to 127.0.0.1 closed.
$ vi Vagrantfile
$ vagrant reload
```

###web хуудсаа үзэх
browser дээр "192.168.33.10" ороход доорхтой адилаар "Hello World!" гэж гарч ирэх болно.

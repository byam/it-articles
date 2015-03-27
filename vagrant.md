#Vagrant

##1. Vagrant гэж юу вэ?
### Товчхондоо
- Virtual machine control

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
# web server ажиллуулах
$ sudo service httpd start

# restart хийх үед мөн ажиллуулах
$ sudo chkconfig httpd on

# firewall унтраах
$ sudo service iptables stop

# restart хийх үед мөн унтраах
$ sudo chkconfig iptables off
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

## 5. Common Folder

CentOS доторх `/vagrant/` болон тухайн компьютерын `/myCentOSVM/` нь ижил юм. 

CentOS:

```sh
[vagrant@vagrant-centos64 ~]$ cd /vagrant/
[vagrant@vagrant-centos64 vagrant]$ ls
Vagrantfile
```

Mac:

```sh
$ cd myCentOSMV
$ ls
Vagrantfile
```

### Хэрэглээ

`/vagrant` дотор `.html` файл байрлуулж, түүнийгээ `symbolic link` ашиглан `/var/www/html` тай холбох. Mac дээр хийсэн өөрчлөлт нь шууд CentOS дээр өөрчлөгдөнө гэсэг үг юм.

```sh
[vagrant@vagrant-centos64 ~]$ mkdir /vagrant/html
[vagrant@vagrant-centos64 ~]$ sudo rm -rf /var/www/html/
[vagrant@vagrant-centos64 ~]$ sudo ln -fs /vagrant/html /var/www/html
```

Mac OS дээр `.html` файл шинээр үүсгэж, тэр CentOS web server дээр харагдахыг харья.

```sh
$ cd myCentOSVM
$ cd html
$ vi index.html
	<h1> Hello from Mac OS!!! </h1>
```

Үүний дараа http://192.168.33.10 ороход өөрчлөгдсөн байха болно.

## 6. Provisioning буюу тохиргоог нэг дор хийх

Vagrant файл дотор `provision.sh` зааж өгнө.

```sh
Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.
config.vm.box = "centos64"

# Доорхыг нэмж бичнэ.
config.vm.provision :shell, :path => "provision.sh"

```

`provision.sh` дотор доорх байдлаар **httpd** суулгая.

```sh
sudo yum -y install httpd
sudo service httpd start
sudo chkconfig httpd on
```

vagrant up хэрэв хийгдцэн бол `vagrant provision` гэнэ.

```sh
$ vagrant provision
```

## 7. Box  шинээр үүсгэх

Одоо байгаа фолдер дох Virtual Machine-г package болгон дараа хүссэг үедээ ашиглахаар бэлдэж болно.

### package болгох

```sh
$ cd myCentOSVM
$ vagrant package

# package.box нэрээр шинээр үүссэн байх болно
$ ls
Vagrantfile package.box 
```

### package-аа system дээ нэмэх

```sh
# system -д нэмэх
$ vagrant box add my_box_CentOS64 package.box

# system -д байгаа эсэхийг шалгах
$ vagrant box list
centos64        (virtualbox, 0)
my_box_CentOS64 (virtualbox, 0)

$ ls ~/.vagrant.d/boxes
centos64        my_box_CentOS64
```

### Хэрэглээ

`my_box_CentOS64` -г ашиглан шинэ Virtual Machine нээе.

```sh
$ mkdir myNewBox
$ cd myNewBox

$ vagrant init my_box_CentOS64

$ vagrant up
```

## 8. Plugin суулгах

```sh
$ cd myCentOSVM

# sahara plugin суулгах
$ vagrant plugin install sahara

# plugin-н заавар харах
$ vagrant plugin -h
Usage: vagrant plugin <command> [<args>]
Available subcommands:
     install
     license
     list
     uninstall
     update
For help on any individual command run `vagrant plugin COMMAND -h`

$ vagrant plugin list
sahara (0.0.17)
vagrant-share (1.1.3, system)
```

## 9. Sahara Plugin ашиглах

sahara-sandbox нь virual machine-д ямар нэг зүйл суулгасны дараа өөрчлөлт орон түүнийг өмнөх байдал руу нь буцаамаар байгаа үед хэрэглэхэд тохиромжтой.

```sh
# sahara байгаа эсэхийг шалгах
$ vagrant plugin list
sahara (0.0.17)
vagrant-share (1.1.3, system)

# sahara-н sandbox on болгох 
$ vagrant sandbox on
[default] Starting sandbox mode...
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%

$ vagrant sandbox status
[default] Sandbox mode is on
```

### sandbox on үед Virutal Machine `test` гэсэн файл шинээр үүсгэе.

```sh
$ vagrant ssh
[vagrant@vagrant-centos64 ~]$ touch test
[vagrant@vagrant-centos64 ~]$ ls
test
```

### Үүсгэсэн `test` гэсэн файл нь ямар нэг өөрчлөлт оруулан, өмнөх байдал руугаа шилжмээр байгаа бол:

```sh
[vagrant@vagrant-centos64 ~]$ exit
logout
Connection to 127.0.0.1 closed.

# өмнөх байсан руугаа шилжих
$ vagrant sandbox rollback
[default] Rolling back the virtual machine...
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%

$ vagrant ssh
Last login: Fri Mar 27 09:40:43 2015 from 10.0.2.2
[vagrant@vagrant-centos64 ~]$ ls

```

### Үүсгэсэн `test2` гэсэн файл нь амжилттай болсон бол `commit` хийнэ:

```sh
# test 2 файл үүсгэх
[vagrant@vagrant-centos64 ~]$ touch test2
[vagrant@vagrant-centos64 ~]$ exit
logout
Connection to 127.0.0.1 closed.

$ vagrant suspend
==> default: Saving VM state and suspending execution...

# commit хийх
$ vagrant sandbox commit
[default] Committing the virtual machine...
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
```

### Sandbox унтраaх

```sh
$ vagrant suspend

$ vagrant sandbox off
[default] Stopping sandbox mode...
0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%

$ vagrant sandbox status
[default] Sandbox mode is off
```


## Хэрэглэсэн материал

* http://dotinstall.com/lessons/basic_vagrant
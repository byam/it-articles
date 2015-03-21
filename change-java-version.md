# Change Java Versions

### show existing java versions

```sh
$ /usr/libexec/java_home -V
Matching Java Virtual Machines (2):
    1.8.0_40, x86_64:	"Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home
    1.7.0_75, x86_64:	"Java SE 7"	/Library/Java/JavaVirtualMachines/jdk1.7.0_75.jdk/Contents/Home

/Library/Java/JavaVirtualMachines/jdk1.8.0_40.jdk/Contents/Home
```

### change java versions

```sh
# show current version
$ java -version
ava version "1.7.0_75"
Java(TM) SE Runtime Environment (build 1.7.0_75-b13)
Java HotSpot(TM) 64-Bit Server VM (build 24.75-b04, mixed mode)

# To change java version 1.7 to 1.8
# set your JAVA_HOME in your shell startup . file
# mine is ~/.zshrc
$ vi ~/.zshrc
	# Change the following codes to your ~/.zshrc
	
	# inactive your java version 1.7
	# export JAVA_HOME=$(/usr/libexec/java_home -v 1.7)
	
	# active your java version 1.8
	export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)
	
# run your ~/.zshrc file
$ source ~/.zshrc

# check current java version
$ java -version
java version "1.8.0_40"
Java(TM) SE Runtime Environment (build 1.8.0_40-b27)
Java HotSpot(TM) 64-Bit Server VM (build 25.40-b25, mixed mode)
```

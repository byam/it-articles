# Terminal-аас Sublime Text дээр файл нээх

## subl-г идэвхижүүлэх

Sublime Text нь terminal дээр ``subl`` гэсэн командаар ажиллах ба доорх байдлаар командыг идэвхижүүлнэ.

```sh
# Mac OS X дээр Sublime Text 2 ашиглаж байгаа бол
$ sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/bin/subl
```

## subl командууд

Амжилттай идэвхижсэн бол доорх байдлаар ашиглана.

```sh
# file.txt гэсэн файлыг Sublime Text дээр нээх
$ subl file.txt

# Sublime Text дээр одоо байгаа фолдеруудыг харуулдаг болгох
$ subl .
```

### Бусад хэрэглээг харах

```sh
$ subl --help
Sublime Text 2 Build 2221

Usage: subl [arguments] [files]         edit the given files
   or: subl [arguments] [directories]   open the given directories
   or: subl [arguments] -               edit stdin

Arguments:
  --project <project>: Load the given project
  --command <command>: Run the given command
  -n or --new-window:  Open a new window
  -a or --add:         Add folders to the current window
  -w or --wait:        Wait for the files to be closed before returning
  -b or --background:  Don't activate the application
  -s or --stay:        Keep the application activated after closing the file
  -h or --help:        Show help (this message) and exit
  -v or --version:     Show version and exit

--wait is implied if reading from stdin. Use --stay to not switch back
to the terminal when a file is closed (only relevant if waiting for a file).

Filenames may be given a :line or :line:column suffix to open at a specific
location.
```
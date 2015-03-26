# Sublime Text дээр Package Control суулгах

## Package Congrol суулгах

1. Sublime Text -г ажиллуулна.
2. `ctrl+` эсвэл `View > Show Console`
3. Доорхийг хуулж бичээд `Enter` дарна.
	* Sublime Text 2
		
		```
		import urllib2,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
		```
	
	* Sublime Text 3
		
		```
		import urllib.request,os,hashlib; h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
		```

4. Sublime Text-ээ Restart   хийнэ.

## Суусан эсэхийг шалгах

1. Sublime Text-ийг нээж `Command+Shift+P` дарна.
2. `Package Control` гэж бичихэд гарч ирж байвал амжилтай суусан гэсэн үг.


## Хэрэглээ

`Package Congtrol` ашиглан **theme** суулгая.

[Curiosity](http://devthemez.com/themes/curiosity) гэсэн theme суулгая.

1. Sublime Text-ийг нээж `Command+Shift+P` дарна.
2. `Package Control: Install Package` гэж бичэн сонгоно.
3. `Theme Curiosity` гэж бичэн theme-ээ татаж авна.
4. Татаж дууссаны дараа `command +  ","` дарж доорх байдлаар бичнэ.
	
	```
	{
		"theme": "Curiosity.sublime-theme",
		"color_scheme": "Packages/Theme - Curiosity/curiosity.base16.tmTheme"
	}

	```
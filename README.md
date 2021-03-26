# manpage_generator
genereates a formatted html page  of all the operating systems man pages 

#toto: parse out non-existing manpages

```
(
mkdir man_pages
echo -e '<!DOCTYPE html> \n<html> \n<body> \n<pre>'  >> index.html
for i in $(compgen -c | sort -h); do echo -e "\n<A HREF=man_pages/$i.html>$i</A>" >> index.html; done	
for i in $(compgen -c | sort -h); do echo -e '<!DOCTYPE html> \n<html> \n<body> \n<pre>'  >> "man_pages/""$i"".html"; done
for i in $(compgen -c | sort -h); do man "$i" >> "man_pages/""$i"".html"; done
echo -e '\n</body> \n</html> \n</pre>' >> "man_pages/""$i"".html"
for i in $(compgen -c | sort -h); do echo -e '<!DOCTYPE html> \n<html> \n<body> \n<pre>'  >> "man_pages/""$i"".html";done
echo -e '\n</body> \n</html> \n</pre>' >> index.html 
open index.html
)
```

#based on this
#save manpages for every command your user can run in one file
```
for i in $(compgen -c | sort -h); do man "$i" >> man.pages."$(date +%F)"; done
```

---
layout: post
author: cbdRedGG
title: Permisos especiales en Linux
---

### Sticky Bit

Uno de los **permisos especiales** de acceso de ficheros y directorios

Su objetivo es que **solo el creador pueda eliminar o renombrar un archivo** en sistemas donde los usuarios tengan permisos de escritura y lectura

La forma en que se aplica el *Sticky Bit* a un fichero o directorio es con:

	chmod +t file/dir
	chmod 1755 file/dir


### SUID

Permite que un binario se ejecute **con los permisos del propietario**. Se identifica mediante una **s** o **4000** en octal. Este permiso **no aplica a directorios**

	chmod u+s script.sh
	chmod 4755 script.sh

### SGID

Permite que un binario se ejecute **como si fuese miembro del grupo al que pertenece el archivo**

Si se establece en un directorio, cualquier archivo creado se le asignara como grupo perteneciente el grupo del directorio

	chmod g+s file/dir
	chmod 2755 file/dir


Es posible usar la notación octal para asignar todos los permisos especiales de la misma manera que los permisos tradicionales:

	chmod 7755 file

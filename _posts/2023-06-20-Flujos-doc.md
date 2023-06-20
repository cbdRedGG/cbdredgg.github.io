---
layout: post
author: cbdRedGG
title: Control de flujos
---


Flujos:
+ **stderr** : *standard error*. Referenciado con el fd (*file descriptor*) **2**
+ **stdout** : *standard output*. Referenciado con un 1
+ **stdin** : *standard input*. 

Redirecciones de flujos:

+ **2>&1** : Redirigir el **stderr** al **stdout**
+ **&>** : Redirigir **stderr** y **stdout**


Ejemplo de redirigir flujos:
```bash
burpsuite &>/dev/null & disown
```
Para que no muestre ningún flujo y ademas se ejecute en background sin dependencia del proceso principal

---
layout: post
author: cbdRedGG
title: Colours, exit status and mouse hiding
---

- - -

### Colours, exit function and mouse hiding

These chunks of code allows the use of **colours** inside scripts and **trapping Ctrl + C** key binding to abort execution
with exit status of `1`.

Finally, if we are executing a loop or any code that forces mouse to blink on screen, we can **hide it using 2 statements**.


### Colours

```bash
#Colours
endColour="\033[0m\e[0m"
greenColour="\e[0;32m\033[1m"
redColour="\e[0;31m\033[1m"
blueColour="\e[0;34m\033[1m"
yellowColour="\e[0;33m\033[1m"
purpleColour="\e[0;35m\033[1m"
turquoiseColour="\e[0;36m\033[1m"
grayColour="\e[0;37m\033[1m"
```

Example of use:

```bash
echo -e "${redColour}Testing ${yellowColour}with ${grayColour}colours${endColour}"
```

Flag `-e` allows the interpretation of special characters


### Ctrl + C function

```bash
function ctrl_c(){
	echo -e "\n\n [!] Exiting ... \n"
	exit 1
}

trap ctrl_c INT
```


### Hide beam

```bash
# Hide cursor
tput civis

# Return cursor
tput cnorm
```

Keep in mind, if you **don't spawn mouse back** it won't appear unless you state the return for it. So, if you **handle script abortion** remember to **add the return
cursor inside** that function

**What is Linux shell**
a shell provide an environment to a user execute commands and interact with kernel 

**Type of shell**
- bash 
- sh 
- ksh
- tsh
- fish
- zsh


**Check bash type**

````
echo $0 
````

 **What is shell Scripting** 
- shell script consist of set of commands to perform a task 
- all the commands executed sequentially
- some task like file manipulation program execution, user interaction, automation task etc can be done

**OS version information Linux**
```
cat /etc/os-release
```

**First Basic Script**
```#!/bin/bash
echo "Hello world"
```

**What is SHEBANG**
```
#!/bin/bash
#SHEBANG tell computer to use bash as shell 
```

**How to Run a Script**
- make sure script has execute permission 
```
rwx
```

**Run using** 
```
./script.sh
OR
/path/script.sh
OR
bash script.sh
```


> Ctrl+C  to terminate
> Ctrl+Z to Stop

**Check User Permission**
```
ls -ltr
```

**Change Permission** 
```
chmod +x script.sh
```

**Without Changing Permission** 
```
bash script.sh
```

Comments 
single line command
```
# this is a comment
```
multi-line comment
```
<<comment
...
your comment here
...
comment
```

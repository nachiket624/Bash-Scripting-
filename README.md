# **What is Linux shell**
a shell provide an environment to a user execute commands and interact with kernel 

**Type of shell**
- bash 
- sh 
- ksh
- tsh
- fish
- zsh


# **Check bash type**

````
echo $0 
````

# **What is shell Scripting** 
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

# Comments 
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

# Variables
```
var_name = value
var_name = $(hostname)
echo $var_name
```

*02_varibable.sh*
```
#!/bin/bash
a = 10
name = "Hello"
echo "My name is $name and age is $age"
```
How to user system define variable 
```
#!/bin/bash
a = 10
name = "Hello"
echo "My name is $name and age is $age"
HOSTNAME = $(hostname)
echo "Name of this machine is $HOSTNAME"
```

# Constant variable
>Once you define a variable and don't want to change it until end of the script

```
readonly var_name = 'hi'
```

03_constant_var.sh
```
#!/bin/bash
#constant variable
readonly COLLAGE = 'abc'
echo "The Collage Name is $COLLAGE"
```

# Array
How to define an array?
```
myArray = (1 2 hello "Hy")
```
How to get values from an array
```
echo "${myArray[0]}"
echo "${myArray[1]}"
```

 04_array.sh
 ```
#!/bin/bash
myArray = (1 2 hello "Hy")
echo "all the value in array ${myArray[*]}"
echo "${myArray[0]}"
echo "${myArray[1]}"
#how to get length of array --> use # befor variable name
echo "The lenght of arrya is ${#myArray[*]}"
#how to get specific value
echo "Value from 2 to 3 ${myArray[*]:2:2}"
#how to update array
myArray += (NewValue 20 40)
echo "Updated array is ${myArray{*}}"

```
output 

# Array KEY-VALUE
```
declare -A myArray
myArray = ( [name]=john [age]=25)
echo "${myArray[name]}"
```

04_key_value.sh
```
#!/bin/bash
#how to store key value pair
declare -A myArray
myArray([name]=john [age]= 50, [location] ='NY')
echo "Name is ${myArray[name]}"
echo "age is ${myArray[age]}"
echo "location is ${myArray[location]}"
```

# String Operations

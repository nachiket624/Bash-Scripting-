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

 myVar = "Hello World!"
 lenght=${#myVar}
 upper=${x^^}
 lower=${y,,}
 replace=${myVar/World/Buddy}
 slice={myVar:6:11}

05_String_Operation_lenght
```
#!/bin/bash
# check lenght of the string
myVar = "Hy Hello"
myVarlength = ${#myVar}
echo "length of the myVar is $myVarlength"
```
06_String_Operation_upper_lower
```
#!/bin/bash
# convert string to upper case and lower case
myVar = "Hy Hello"
echo "Upper case is ${myVar^^}"
echo "Lower case is ${myVar,,}"
```
replace a word in string 
syntax
>{variable_name/word_to_replace/new_word}

07_String_Operation_replace

```
#!/bin/bash
myvar = "Hey Buddy, how are you?"
newvar = #{myvar/Buddy/Bob}
echo "New variable is ${newvar}"
```

08_String_Operation_slice
```
#!/bin/bash
myvar = "This is long string"
newvar = "After slice #{myvar:4:6}"
```

# User Interaction 
read <var_name>
read -p "Your name" Name

09_user_input
```
#!/bin/bash
echo "What is your name"
read name 
echo "Your name is $name"
read -p "What is your name " name
echo "Know your name is $name"
```

# Arithmetic Operations


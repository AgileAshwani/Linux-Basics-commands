[<<Chapter1](commands.md)

### Basic Shell Scripting

* **Regular Expressions**
* *Metacharacters*
* Wildcards


















```bash
# Below line indicates which shell will be used. e.g, sh,csh,bash
#!/bin/bash

clear
echo "Name:"
read name
mkdir /home/ashwanik81/$name
touch /home/ashwanik81/$name/$name
echo "The file $name created"
```


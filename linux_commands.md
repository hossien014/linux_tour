# linux(ubunto) COMMAND
- switch to root $  
```bash
   sudo dpkg -r package
   ```

 - switch users  $ 
 ```bash 
      su -targetUser
 ```
 
 - delete users  $ 
```bash
   sudo deluser postgres
   ```
   - add environment variable
   ```bash
      export MY_VARIABLE_NAME=VALUE
   ```
   - remove environment variable
   ```bash
      unset MY_VARIABLE_NAME
   ```
   - print all environment variables
   ```bash
     printenv
   ```
   - add root privilege to user 
   ```bash
     sudo usermod -aG sudo [tagetuser]
   ```
   - Search file 
   ```bash
      find -name name_of_file # this serach from currnt directory for the file
      find -iname name_of_file # iname is for case insensitive
      find . -iname '*.py' # all file with .py suffix
      find . -type d -iname *somename* # find dirctory
      find /path/to/search -size <size_of_the_file> #find by size 
     find [directory] -type f -iname [name of file]
     find ~ -type f -iname *.swp
   ```
   [read more about find coomand](#https://www.freecodecamp.org/news/how-to-search-files-in-the-linux-terminal/#:~:text=By%20passing%20the%20name%20of,the%20location%20of%20the%20file.&text=But%20remember%20the%20%2Dname%20flag,use%20the%20%2Diname%20flag%20instead.)
   - show ports
   ```bash
      netstat -a #list of all ports 
      netstat -at #only tcp port 
      netstat -au #only udp port 
      netstat -l #active ports 
      netstat -lt #active tcp ports 
      netstat -lu #active udp ports 
      netstat -tuln 
      netstat -tuln | grep 8000

   ```

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

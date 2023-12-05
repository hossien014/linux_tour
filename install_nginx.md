1-  sudo apt install nginx

2- sudo systemctl start nginx.
      now type localhost in browsr you can see nginx defult page 

3- you can change nginx config to redirect user to different location 
      open this file 
```etc/nginx/sites_available/defult ```
      add this text in location / 
``` bash 
      server {
        listen 80 default_server;
        listen [::]:80 default_server;

        server_name _; # replace with specific domain name like sanjeev.com
        
        location / {
                proxy_pass http://localhost:8000;  # ever request will redirect to por 8000
                
                proxy_http_version 1.1;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header Upgrade $http_upgrade;
                proxy_set_header Connection 'upgrade';
                proxy_set_header Host $http_host;
                proxy_set_header X-NginX-Proxy true;
                proxy_redirect off; 
        }

}

```

## diagnose nginx failur

```bash
      sudo nginx -t #check nginx config for syntax error 

      sudo netstat -tuln # check if target port used by another app 

      sudo tail -f /var/log/nginx/error.log # check log file 

```
The error message you provided indicates that the Nginx service failed to start. The key part of the error message is this:

```
Process: 1936 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=1/FAILURE)
```

This suggests that there is an issue with the Nginx configuration or setup that is preventing it from starting. To diagnose and fix the problem, you can follow these steps:

1. Check Nginx Configuration:
   You should start by checking the Nginx configuration for syntax errors. You can do this by running the following command:

   ```
   sudo nginx -t
   ```

   This command will test the Nginx configuration for any syntax errors. If there are errors, it will provide information about where the errors are in the configuration file. You will need to edit the configuration file and correct any issues.

2. Check for Permission Issues:
   Ensure that Nginx has the necessary permissions to access its configuration files and web content. The Nginx service should be running as the user "nginx" or "www-data," depending on your system. Verify that the configuration files and web content directories are owned by the correct user and group. You can use the `ls -l` command to check file ownership and permissions.

3. Check for Port Conflicts:
   Make sure there are no other services running on the same ports that Nginx is configured to use (usually port 80 for HTTP and 443 for HTTPS). You can check for listening ports using the `netstat` or `ss` command:

   ```
   sudo netstat -tuln
   ```

   If another service is using the same port, you may need to stop or reconfigure it.

4. Review Nginx Error Logs:
   Check the Nginx error logs for more information about the failure. The error logs are typically located in the `/var/log/nginx/` directory. You can view the error log using a command like:

   ```
   sudo tail -f /var/log/nginx/error.log
   ```

   This will display the last few lines of the error log and may provide more details about the specific issue that caused Nginx to fail.

5. System Resource Issues:
   Ensure that your server has enough system resources (CPU, memory, disk space) available for Nginx to run. Resource constraints can lead to service failures.

6. Check for SELinux or AppArmor:
   If you are using SELinux (Security-Enhanced Linux) or AppArmor, ensure that the security policies are not preventing Nginx from starting. Check the audit logs or AppArmor logs for related denials.

After identifying and resolving the specific issue, you can attempt to start Nginx again using the `systemctl` command:

```
sudo systemctl start nginx
```

If you encounter any issues or need further assistance, please provide additional details about your configuration, and I can offer more specific guidance.
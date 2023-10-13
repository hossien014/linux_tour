- you should make a file in below directory
``` 
/etc/systemd/system
```
- file should have .service suffix 
```
name.service
```
- content of file should look like below text
``` bash
[Unit]
# you can write every thing you want here
Description=demo fastapi application

# this service start affter internet   
After=network.target 

[Service]
User=[username]  # waht user run service 
Group=[username]
WorkingDirectory=/home/[username]/app/src/ 
Environment="PATH=/home/[username]/app/venv/bin"
EnvironmentFile=/home/[username]/.env     
ExecStart=/home/[username]/app/venv/bin/gunicorn -w 4 -k uvicorn.workers.UvicornWorker app.main:app --bind 0.0.0.0:8000

[Install]
WantedBy=multi-user.target
```

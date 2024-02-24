# githubviewers

## Deploy in Linux
```shell
#1. Install php-curl:
sudo apt-get install php-curl

#2. Run the PHP server in the background:
nohup php -S localhost:8000 > output.log &

#3. nginx 
location /githubviewers/ {
       proxy_pass http://localhost:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
```



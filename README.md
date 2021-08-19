### Installation
Install Docker Deskop

cd into nginx-proxy and run ```docker network create nginx-proxy``` followed by ```docker-compose up -d```

Windows: click start and type Notepad, right click and open as Administrator. Click File->Open-> C:\Windows\System32\drivers\etc\hosts
In hosts add ```127.0.0.1        my-app-2.test``` at the bottom

in root ```git clone git@github.com:rbaskam/docker-multi-app-base.git my-app-2.test```

cd into my-app-2.test Delete the .git from root then cd into src and run rm README.md then ```composer create-project laravel/laravel .```
```cd ..```
In the ```docker-compose.yml``` change all the container_name (8 ish of them) to something unique e.g nginx_four to nginx_five
Then change all the ports to something unique only the first part so - 3306:3306 becomes - 3307:3306

Change the virtual host to match your app
```
environment:
      VIRTUAL_HOST: my-app-2.test
```

```docker-compose up -d --build```

Guides
https://stackoverflow.com/questions/63711263/how-to-show-laravel-home-page-in-docker-using-jwilder-whoami

https://github.com/aschmelyun/docker-compose-laravel

https://francoisromain.medium.com/getting-started-with-docker-for-local-node-js-development-192ceca18781

https://francoisromain.medium.com/set-a-local-web-development-environment-with-custom-urls-and-https-3fbe91d2eaf0

https://danielstoyanoff.medium.com/create-friendly-urls-for-your-local-dockers-3b35f676c341
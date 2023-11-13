## Docker Simple HTML Viewer

### Introduction
This docker container is intended for viewing html files only.  
You can use this docker to running simple html, html templates, react templates and many more.

### Pre-Requisites
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Git](https://git-scm.com/downloads)

### Clone this repository
```
$ git clone https://github.com/djono/docker-simple-html-viewer.git
```

Project structure:
```
.
├── README.md
├── compose.yaml
├── build
│   └── Dockerfile
├── config
│   └── apache2
└── html
    └── index.html
```
**README.md** - This instructions file

[**compose.yaml**](compose.yaml)
```
services:
  web:
    build:
      context: build
      target: builder
    container_name: "MAZJOHN-HTML-VIEWER"
    ports: 
      - '8080:80'
    volumes:
      - ./html:/var/www/html/
      - ./config/apache2:/etc/apache2/
```

**build** - Directory with Dockerfile for building the image.  
[**Dockerfile**](build/Dockerfile) - for building the image.  
**config** - Directory with apache2 and Others configuration file.  
**apache2** - Directory with apache2 configuration file.  
**html** - Put your awesome HTML files over here.  
[**index.html**](html/index.html) - Sample html file.

### Deploy with docker compose

```
$ docker-compose up -d
```

After the application starts, navigate to `http://localhost:8080` in your web browser or run:
```
$ curl localhost:80
```

Stop and remove the containers
```
$ docker-compose down
```
That's it and have fun.   
by [mazjohn.com](https://mazjohn.com)

License
----
[MIT License](LICENSE)
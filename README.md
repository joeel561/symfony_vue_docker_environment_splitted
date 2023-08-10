# Symfony Vue Splitted Docker Environment

### 1. create a Symfony Project named api with this command

```
symfony new api --version="6.3.*"
```

### 2. cd api/ & install maker bundle

```

composer require symfony/maker-bundle --dev

composer install

```

### 3. go back to the root folder & install the Vue project with vite & call it client

```
npm create vite@latest

```

### 4. cd client 

```

npm install

```

### 5. add --host to the dev build in package.json
```json

  "scripts": {
    "dev": "vite --host",
  }

```

### 6. change .env variables for the database if u need it

```

SYMFONY_APP_PATH=./app

# mysql
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=new_docker_project_db
MYSQL_USER=root
MYSQL_PASSWORD=root

```

### 9. add base controller in symfony to test if it's working

``` 

php bin/console make:contoller Base

```

```php

class BaseController extends AbstractController
{
    #[Route('/', name: 'app_base')]
    public function index(): Response
    {
        return $this->render('base.html.twig');
    }
}

```


### at the end docker compose build & docker compose up to run the local environment 🍑 VUEjs Port runs on 5173 & symfony port on 8000 & mysql 3306
# Zerops Hello Worlds

```yaml
project:
  name: zerops-hello-worlds
  tags:
    - zerops
    - hello-worlds

services:
  - hostname: rust1
    type: rust@1
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    ports:
      - port: 8080
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: phpnginx81
    type: php-nginx@8.1+1.22
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: phpnginx83
    type: php-nginx@8.3+1.22
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    nginxConfig: 

    minContainers: 1

  - hostname: phpapache81
    type: php-apache@8.1+2.4
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: phpapache83
    type: php-apache@8.3+2.4
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: nodejs20
    type: nodejs@20
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
      NODE_ENV: production
    ports:
      - port: 3000
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: golang1
    type: go@1
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    ports:
      - port: 8080
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: dotnet60
    type: dotnet@6
    envSecrets:
      ASPNETCORE_URLS: http://*:5000
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    ports:
      - port: 5000
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1

  - hostname: python39
    type: python@3.9
    envSecrets:
      DB_HOST: db
      DB_NAME: db
      DB_PASS: ${db_password}
      DB_PORT: "5432"
      DB_USER: ${db_user}
    ports:
      - port: 5000
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds
    minContainers: 1
    maxContainers: 6

  - hostname: nginx
    type: nginx@1.22
    ports:
      - port: 80
        httpSupport: true
    enableSubdomainAccess: true
    buildFromGit: https://github.com/jansaidl/zerops-hello-worlds

  - hostname: adminer
    type: php-apache@8.1+2.4
    buildFromGit: https://github.com/zeropsio/recipe-adminer@main
    enableSubdomainAccess: true
    minContainers: 1
    maxContainers: 1

  - hostname: db
    type: postgresql@14
    mode: NON_HA
    priority: 1
```


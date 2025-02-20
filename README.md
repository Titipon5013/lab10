# lab10

- docker compose up -d

- 1.3
  
  ![image](https://github.com/user-attachments/assets/717b6dbf-170b-4ef4-b498-5ecbb223b629)

- 1.4 : docker compose down
- 1.5 : docker compose up -d / docker volume ls / docker volume rm lab9_mysql_data

- 2.1
  
  ![image](https://github.com/user-attachments/assets/99be493e-3a38-4fbf-b00e-59c2b500c6e2)

  ![image](https://github.com/user-attachments/assets/7830ee1a-1ef1-42f8-be2e-ef35c1b2dd36)


- 2.2 : docker build -t timetitipon/test:2.0 . / docker push timetitipon/test:2.0 (on powershell)
- docker pull timetitipon/test:2.0 / docker run -p 8106:80 timetitipon/test:2.0
  
  ![image](https://github.com/user-attachments/assets/7e2fdca7-eecc-41a9-bb11-b6dcc471b36c)

- 2.3 : docker build -t timetitipon/test:3.0 . / docker push timetitipon/test:3.0 (on powershell)
- docker pull timetitipon/test:3.0 / docker run -p 8106:80 timetitipon/test:3.0

  ![image](https://github.com/user-attachments/assets/6a011844-3fe7-4acb-9ff8-672717856b3d)

- 2.4 : docker buildx create --use --name mybuilder / docker buildx inspect --bootstrap
- 2.5 : docker buildx build --platform linux/amd64,linux/arm64 -t timetitipon/myimage:latest .
- 2.6 : docker buildx build --platform linux/amd64,linux/arm64 -t timetitipon/myimage:latest --push .


- 3

  ![image](https://github.com/user-attachments/assets/6f2c3cd8-7d37-49e1-aeff-1b62960d1392)

- touch docker-compose.yml
- vi docker-compose.yml
- insert : services:
  mongo:
    image: mongo:latest
    ports:
      - "27017:27017"
    environment:
      MONGO_INITDB_ROOT_USERNAME: root
      MONGO_INITDB_ROOT_PASSWORD: example

  mongo-express:
    image: mongo-express:latest
    depends_on:
      - mongo
    ports:
      - "8081:8081"
    environment:
      ME_CONFIG_MONGODB_ADMINUSERNAME: root
      ME_CONFIG_MONGODB_ADMINPASSWORD: example
      ME_CONFIG_MONGODB_SERVER: mongo
- cat docker-compose.yml
- docker-compose up -d
- see on 8081 port



  

# node-prisma

This application runs a Graphql API using Apollo Server with Prisma ORM and Postgres DB.
## Run Locally

You need to have [nodejs](https://nodejs.org/en/) and npm installed to run this application

Clone the project

```bash
  git clone https://github.com/kamransarwar47/node-prisma.git
```

Go to the project directory

```bash
  cd node-prisma
```

Install dependencies

```bash
  npm install
```

## Docker Compose

If you have docker and docker-compose installed you can use the `docker-compose.yml` configuration to run postgres DB instance inside a docker container.


### Environment Variables

To run this container, you will need to update the following environment variable in your `docker-compose.yml` file.

```
environment:
- POSTGRES_USER=db_username
- POSTGRES_PASSWORD=db_password
```

After this you can run this command to run the container.

```bash
  docker-compose up -d
```

If you do not have docker installed then you need to have a running Postgres DB instance.


### Environment Variables

To run this project, you will need to rename `.env.example` file to `.env` and update the following environment variable in your `.env` file with correct DB username and password credentials.

`DATABASE_URL="postgresql://db_username:db_password@localhost:5432/posts_db?schema=public"`


Run the following command to create and deploy Database Migration.

```bash
  npx prisma migrate dev --name "init" 
```

Start the server

```bash
  npm start
```

You will see the following message in console

```
  Server runs at: http://localhost:9090
```


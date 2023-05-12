# Fullstack Monorepo template

Next.js 13 and Hasura project template.

## Setup

### Step 1 Setup Hasura

1. Create api/hasura.env , you can use .env.example as a starting point
2. Start local hasura instance by running `cd api/ && docker compose up -d`
3. While in `api/` you can start the Hasura console `yarn hasura console`
4. You can access pgadmin4 on http://localhost:5050 login details are in the docker-compose file

### Step 2 Connect Hasura to source database

When starting from scratch:

1. Set the env variable `PG_DATABASE_URL` appropriately. If you copied .env.example, this defaults to the posgres docker container installed with Hasura. Doesn't have to though!
2. In the Hasura console, click the data tab then connect to existing database

### Step 3 Apply Hasura Metadata

When using the fully configured template:

1. Run `yarn hasura metadata apply` to load the latest
2. Login the the hasura console with `yarn hasura console` - any configuration or database changes will be tracked and can later be applied as migrations or metadata - more information in this doc https://hasura.io/docs/latest/migrations-metadata-seeds/overview/

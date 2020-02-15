# Favorites API

Example of a simple implementation to build a favorites api on top of Redis

#### Related repositories

- [Favorites API](https://github.com/Eyevinn/favorites-api)
- [Ratings API](https://github.com/Eyevinn/ratings-api)
- [Stream Limit API](https://github.com/Eyevinn/stream-limit-api)

## Requirements

- nodejs v10+
- redis

## Usage
- `git clone git@github.com:Eyevinn/favorites-api.git`
- `cd favorites-api`
- `npm install`
- Start Redis locally or insert the needed keys into the .env file
- `npm start` to run the server

## Endpoints

- POST `/favorites/:userId/:assetId` To add an asset as favorite
- DELETE `/favorites/:userId/:assetId` To remove an asset from favorites
- GET `/favorites/:userId` to get all favorites for a specific user, newest first.

## Environment variables

- `NODE_ENV` if set to `development` there will be some logging made into the console
- `REDIS_URL` if not local
- `REDIS_PORT` if not default (6379)
- `REDIS_AUTH`

## Docker

A `docker-compose` config file is provided that takes care of building the image and running this container together with a Redis db container.

Start the service:

- `docker-compose up`

Stop the service:

- `docker-compose down`

The Redis container is using `/tmp` as persistant storage but this can be changed by modifying the `docker-compose.yml` file. Change:

```
    volumes:
      - /tmp:/bitnami/redis/data
```

to where you want the persistant storage to be located.

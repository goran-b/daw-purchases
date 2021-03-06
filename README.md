# Purchases API

A sample API for Discount Ascii Warehouse

## Install and start the server

- `npm install`
- `npm start`

You can also specify the port to listen on (default is `8000`): `PORT=3456 npm start`

Now you can make API requests, eg: `curl -i localhost:8000/api/users/`

## Generating data

- to use the same set of hardcoded data every time, put some files in `.data/`
- if the files aren't found there (or invalid) `src/setup-store.js` will generate random data with [faker](https://npm.im/faker)
- you can also run `./bin/generate-data.js` to see an example of random data

## API Reference

### GET purchases/by_user/:username

- params:
  - username (string)
  - ?limit (int)

- response (json):

```
{
  "purchases": [
    {
      "id": (int),
      "productId": (int),
      "username": (string),
      "date": (iso8601 string)
    },
    ...
  ]
}
```

### GET purchases/by_product/:productId

- params:
  - productId (int)
  - ?limit (int)

- response: same as `GET purchases/by_user/:username`

### POST purchase

- body (json):

```
{
  "username": (string)
  "productId": (int)
}
```

### GET products/:id

- params:
  - id (int)

- response (json):

```
{
  "id": (int),
  "face": (string),
  "size": (int),
  "price": (int)
}
```

### GET users

- params:
  - ?limit (int)

- response (json):

```
{
  "users": [
    {
      "username": (string),
      "email": (string)
    },
    ...
  ]
}
```

### GET users/:username

- params:
  - username (string)

- response (json):

```
{
  "username": (string),
  "email": (string)
}
```

Maintained by the [developers at x-team](https://www.x-team.com) | [developer blog](https://www.x-team.com/blog/)

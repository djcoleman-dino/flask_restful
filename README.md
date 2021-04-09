# Flask Restful API

### UserLogin

- `POST: /login`
  - Description: authenticate a user and ,if authenticated, respond with a fresh access token and a refresh token.

### TokenRefresh

- `POST: /refresh`
  - Description: This endpoint is used to refresh an expired access token. If the refresh token is valid, respond with a new valid access token (non-fresh).
  - Request header: `Authorization Bearer <refresh_token>`

### Item

- `GET: /item/<name>`
  - Description: get an item by name, require a valid access token to access this endpoint.
  - Request header: `Authorization Bearer <access_token>`
- `POST: /item/<name>`
  - Description: create a new item, require a valid and fresh access token to access this endpoint.
  - Request header: `Authorization Bearer <access_token>`
- `DELETE: /item/<name>`
  - Description: delete an item by name, require a valid access token and admin privilege.
  - Request header: `Authorization Bearer <access_token>`

### ItemList

- `GET: /items`
  - Description: get all items, half protected. User can get more detailed info when providing an access token.
  - Request header: `Authorization Bearer <access_token>`

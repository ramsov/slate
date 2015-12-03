# People

## Get Authenticated User

```curl
curl https://api.bookwhen.com/v1/people/current \
  -u 8itj6o2stks9r5u7mhy742g3fb4g-f22031c16c985ef9e50ab04c5f5c1bf318bb9848cddbdd7dca26dd426a0f2cc1:
```

```json
{
  "person": {
    "id": "11wgzy8pycii",
    "username": "test",
    "email": "test@example.com",
    "is_admin": false
  }
}
```

Retrieve basic information about the current user as authenticated by the OAuth token. If no OAuth2 bearer token is supplied then a 404 _person not found_ message will be returned.

### HTTP Request

`GET https://api.bookwhen.com/v1/people/current`

### Attributes

Attribute   | Description
----------- | -----------
is_admin    | Is the user an administrator of the account?

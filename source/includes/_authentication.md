# Authentication

> Use HTTP Basic authentication for all requests:

```curl
curl https://api.bookwhen.com/v1/events \
  -u 8itj6o2stks9r5u7mhy742g3fb4g:
```

> Replace `8itj6o2stks9r5u7mhy742g3fb4g` with your API Key. Append a colon `:` to prevent it from asking for a password.

All requests must be authenticated using an **HTTP Basic username** and a blank password.

The username **must contain** the **API Key** for your account, and **optionally** an **OAuth2 bearer token** obtained for a particular user. Join the two tokens with a hyphen.

You will soon be able to obtain your API Key from your account settings pages, but for now please <a href="mailto:support@bookwhen.com?Subject=Bookwhen%20API%20Key">get in touch</a>.

> Example of a call authenticated additionally with an OAuth2 bearer token:

```curl
curl https://api.bookwhen.com/v1/events \
  -u 8itj6o2stks9r5u7mhy742g3fb4g-f22031c16c985ef9e50ab04c5f5c1bf318bb9848cddbdd7dca26dd426a0f2cc1:
```

_Note:_ The use of the _OAuth2 bearer token_ embedded in the basic auth username is a little unconventional but 'keeps it simple'.

The OAuth2 endpoints are:

`http://api.bookwhen.com/oauth/authorize`
`http://api.bookwhen.com/oauth/token`

<a href="mailto:support@bookwhen.com?Subject=Bookwhen%20OAuth%20Client">Contact us</a> to set you up with an OAuth2 client ID and secret.

<aside class="notice">
You must replace <code>8itj6o2stks9r5u7mhy742g3fb4g</code> with the API Key for your account. The one shown is for the bookwhen <a href="https://bookwhen.com/example">example page</a>.
</aside>

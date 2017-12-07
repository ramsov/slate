# Authentication

> Use HTTP Basic authentication for all requests:

```curl
curl https://api.bookwhen.com/v1/events \
  -u 8itj6o2stks9r5u7mhy742g3fb4g:
```

> Replace `8itj6o2stks9r5u7mhy742g3fb4g` with your API Key. Append a colon `:` to prevent it from asking for a password.

All requests must be authenticated using an **HTTP Basic username** with a **blank** password.

The username is the **API Key** for your account.

You will able to obtain your API Key from your account settings pages in due course, but for now please <a href="mailto:support@bookwhen.com?Subject=Bookwhen%20API%20Key">get in touch</a>.

> Example:

```curl
curl https://api.bookwhen.com/v1/events \
  -u 8itj6o2stks9r5u7mhy742g3fb4g:
```

<aside class="notice">
You must replace <code>8itj6o2stks9r5u7mhy742g3fb4g</code> with the API Key for your account. The one shown is for the bookwhen <a href="https://bookwhen.com/example">example page</a>.
</aside>

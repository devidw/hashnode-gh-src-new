## How to bake cookies using HTTP: The "Set-Cookie" and "Cookie" HTTP headers

You can create a cookie by adding a `Set-Cookie` HTTP header to an HTTP response.

The client browser which receives that response uses the provided directive to create the actual cookie on the client-side.

For example, an HTTP response header could look like this:

```http
HTTP/2.0 200 OK
Set-Cookie: theme=light
…
```

Your web browser will interpret the `Set-Cookie` header and create a cookie with a  name of `theme` and a value of `light`.

To create multiple cookies, you can provide more than one `Set-Cookie` header to the request. A cookie will be created for each `Set-Cookie` header.

Let's say your application stores the color scheme of the application appearance in that cookie.

Now you decide to switch to dark theme.

Your application makes use of a client-side scripting language like JavaScript to change the value of the `theme` cookie from `light` to `dark`.

Note, that in JavaScript, all cookies are available through `document.cookie`.

The data type of `document.cookie` is string, which means even when you create multiple cookies, there are all stored in one single string (separated by semicolons `;`).

In our example, `document.cookie` is equal to `"theme=dark"`.

When you visit pages under the domain of the newly created cookie, your browser will attach that cookie to every resource you are requesting.

Such an HTTP GET request could like the following one:

```http
GET /some/page HTTP/2.0
Host: david.wolf.gdn
Cookie: theme=dark
…
```

Our browser is adding the `Cookie` header to the request with a name plus value declaration.

## Conclusion
Cookies can be created using `Set-Cookie` header on an HTTP response.

All the existing cookies are transferred using the `Cookie` header on each request to the domain cookies belong to.

---

## Resources

* [wikipedia.org](https://en.wikipedia.org/wiki/HTTP_cookie)
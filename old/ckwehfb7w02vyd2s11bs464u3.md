## Introduction into the Hypertext Transfer Protocol (HTTP)

The Hypertext Transfer Protocol (HTTP) is how web browser (client side) and web server (server side) communicate with each other.

Communication in terms of HTTP means _requests_ and _responses_.

## Request
When you enter a URL in the address bar of your browser and hit enter, your browser requests the webpage connected with the entered URL. This is called an HTTP _request_.

That's how such a `GET` request can look like:

```http
GET /index.html HTTP/2
Host: david.wolf.gdn
```

After sending such a request, DNS will be used to resolve the domain name `david.wolf.gdn` to its [IP address](https://xn--david-9u04d.to/introduction-and-overview-of-the-internet-protocol-ipv4-and-ipv6).

Once the IP address was found, Transmission Control Protocol (TCP) and Internet Protocol (IP) will be used to send the request to the host (`david.wolf.gdn`).

## Response
Once the initial requests find its way to the targeted host, HTTP is used to identify the requested file.

### 200
When the file was found on the host and everything is okay, an HTTP _response_ is sent back to the client.

```http
HTTP/2 200 OK
Date: Tue, 23 Nov 2021 19:39:15 GMT
Server: Apache/2.0.54
Last-Modified: Son, 21 Nov 2021 19:13:03 GMT
Content-Length: 512
Connection: close
Content-Type: text/html
Content: <html>…</html>
```

The HTTP status code `200` in the first line of the HTTP response tells us that the requested file was found and everything is `OK`.

At the bottom of the response, we are receiving the actual `Content`, `<html>…</html>`, of the file send by the web server. 

In this case, it's HTML code, as defined in the MIME-type `text/html` in `Content-Type`.

### 404
When the file is not found on the host, there is nothing that could be send back.

That's when we receive an HTTP error `404`:

```http
HTTP/2 400 Not Found
```

---

And that's it for a short introduction into HTTP.

If I got you interested, there is plenty more to explore for you:

* There are bunch more request methods, in this article you have seen a `GET` request. There are other methods like `POST` to submit data using HTTP. And that's not the end of the story, there are even more.
* Same goes for HTTP response status codes, there are many more.

Have fun checking out the technology!
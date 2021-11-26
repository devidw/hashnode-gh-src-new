## HTTP "Clear-Site-Data": How to force cache clearing for all of your website visitors

Everybody knows this situation: You just rolled out that fresh new feature to your website. It is online now. Yeah. You refresh your website in the browser and … nothing changed …

Well, in most cases this is due to browser caching. 

Modern browsers have smart features includes that allows them to store often requested data to your local disc. Next time you request that given page again, resources will be loaded from your disc instead of downloaded from the server again.

That's caching.

And caching is awesome – thanks to caching technology we can surf sooo much faster, which is super cool.

But, yeah, sometimes we hate caching, because we want everybody out there to download the freshest and newest version of our website.

Which is not that easy, since they have resources cached on their system, which is kind of out of range for us.

Things seem hopeless, but there is a magical option left for us: `Clear-Site-Data`.

`Clear-Site-Data` is an HTTP header, which can be set on the HTTP responses of your web server. 

You can provide different directives to that header, which will tell the client browsers different things to do according to the header.

Possible directives are:

* `"cache"`
* `"cookies"`
* `"storage"`
* `"executionContexts"`
* `"*"`

Note that these directives are only valid with double quotes `"…"`, the quotes are required here!

The client data associated with the name provided in the directive will be cleared by the client, as soon as the client gets a response from your web server, which includes the `Clear-Site-Data` header with a corresponding directive.

So, when you specify `"cache"` as directive for our `Clear-Site-Data` header, all the cached data of the response resource will be removed from the client storage:

 ```
Clear-Site-Data: "cache"
```

That's our solution – that's what we are looking for! 🚀

Also note, that you can even combine these different directives by separating them with commas `,`.

The last mentioned directive in the list above`"*"` is the wildcard expression:

```
Clear-Site-Data: "*"
```

Which is the same as listing all directives:

```
Clear-Site-Data: "cache", "cookies", "storage", "executionContexts"
```

Be careful with the usage of `"*"`, as it includes `"cookies"` and `"storage"`, which will also delete cookies, local storage (`localStorage.clear()`), session storage (`sessionStorage.clear()`) and [more](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Clear-Site-Data) on your clients machines.

That could kill their login sessions or even remove local saved application data!

## Conclusion
When you need to force cache clearing for all your website visitors, the HTTP `Clear-Site-Data` header is a great option to get that done.

Also, when you have to clear other data, such as cookies, `Clear-Site-Data` is the way to go.

## Resources
* [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Clear-Site-Data)
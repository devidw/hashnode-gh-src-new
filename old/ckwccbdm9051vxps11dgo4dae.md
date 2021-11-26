## Let's bake some Cookies: Introduction into Cookies on the Web (HTTP Cookies)

You heard about cookies. 

At least, you get penetrated with these annoying _"we use cookies"_ banners or even dialogue boxes. 

You ever asked yourself what a cookie is? 

In this article we will talk have a closer look onto the topic and by the end you will fully understand what cookies on the web are all about. 

So, let's go ahead and kick it off:  

Cookies are actually files.  

Simple text files with limited size. 

These text files are stored on your machine. 

They are located In a directory on your machine managed by your web browser. 

You might ask yourself, who creates these files and for what are they used, which information is stored in these cookie files? 

Well, we will cover all of this step by step. 

So, cookies are a way for websites and web applications to store small amounts of data in text files on the client computer. 

The stored data will persist for a given time, which can be configured at creation. 

That means cookie data will stay when you refresh or even leave the "cookie-creation-page". 

The cookie files are created by either your web browser or the web server, from which you downloaded the website. 

Because cookies can be created and managed on both sides of the client server architecture, it's absolutely necessary for that cookies to be shipped with the page itself. 

Since we want to make sure that cookies are available at both ends of the architecture equally, this transfer is required. 

Cookie transfer is possible thanks to the hypertext transfer protocol (HTTP). 

When there are cookies set on the client side, they will be attached to the upcoming HTTP requests send to the web server, which delivers the website resources. 

That'a how cookies are transferred from the client side to the server side. 

Any scripting language integrated with the web server, which receives and handles the incoming requests with attached cookies, is now able to make operations on the submitted cookies. 

These operations can include:  
* Deleting a cookie 
* Changing a cookie, for example: 
    * Its name 
    * It's contents 
    * Etc. 
* Creating a new cookie 

These operations can be performed though a server side scripting language like Python or historic PHP. 

Scripting languages like JavaScript are doing the same job on the client side. 

Since cookies are sent to the web server through HTTP, and can be managed on the server side, all updates applied here, have to be transferred back to the client, because cookies are stored on the client side and not on the server. 

This sending back is also possible through HTTP. This time, we attach all these cookies to the response the web server sends back to the client. 

And that's it. That's how cookies are transferred from server to client and vice versa - powered by simply adding the cookies to each request and response between client and server. 

Now that we know how cookies are handled technically, let's jump right into the usage of cookies.

The basic idea of using cookies is, to make data to stay for a given period of time. 

This period of time could be a single browser session. Then the cookies will be deleted when the closing the web browser. 

This is the default behavior and lifetime of a cookie. 

The life of the cookie can also be set to an hour or two or whatever. 

To specify this, you give that cookie a date, at which it will expire. 

When the expiring date is reached, the cookie will be deleted automatically.  

Generally, cookies are used to store information associated with a page visitor.

For example, some use cases for storing such personal information are:

* Authentication
    * To keep the user logged in, even after the page/browser was closed
*  For keeping user data such as:
    * Items in the cart of an online shop
    * Preferred color scheme

Beside others, that's what cookies are used for.

And that's all about cookie for today.

Have a nice one.

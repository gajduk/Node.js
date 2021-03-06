# Reading Material Node.js Week 3

## Agenda

1. Making use of other APIs
   - How to consume an external API?
2. What is a templating engine?

## 0. Video Lectures

Your teacher Andrej has made video lectures for this week's material. You can find them here: [Videos 14 - 18](https://www.youtube.com/playlist?list=PLVYDhqbgYpYXpc_l_Vlj8yz3LjgkkWXnn)

<a href="https://www.youtube.com/playlist?list=PLVYDhqbgYpYXpc_l_Vlj8yz3LjgkkWXnn" target="_blank"><img src="../assets/andrej.png" width="600" height="350" alt="HYF Video" /></a>

## 1. Making use of other APIs

The role of a web server is to serve the user what they want: for example, your user account information, video/images or any other type of data.

Sometimes, in order to get the user what they want the server has to talk to other servers. The way servers talk to each other is no different than how your browser talks to a server. It uses the same HTTP protocol and very often REST and JSON as well.

In a way using APIs serves a similar purpose as using a package from NPM. It allows us to reuse code that someone else has written. In the case of API we do not directly get the code, but we use the functionality that the code provides.

For example, we could use APIs to [authenticate users](https://developers.facebook.com/docs/facebook-login/), [check addresses and locations](https://locationiq.com/#demo), [send emails](https://sendgrid.com/docs/for-developers/sending-email/api-getting-started/) and much more.

As you can see from the examples it would be really difficult to build such services ourselves. Just imagine the security and legal issues involved in building a [payment processing system](https://stripe.com/docs/api)!

Another trendy reason for using APIs is known as "microservices". In a nutshell, microservices is an approach to building web sites where the application is split into many small servers which use APIs to talk to each other. This is a huge topic that we do not have time to cover, but it is really good to know about. To understand it on a high level see the [video](https://www.youtube.com/watch?v=STKCRSUsyP0).

### How to consume an external API?

How to consume an external API. First of all, let's define the terms here.

By `consume` we refer to the act of using the service an API provides, to be used in our own application. This service will be in the form of some kind of data transfer.

For example, let's say we want to get data from the [RandomUser API](https://randomuser.me/api/).

The service the API offers is the provision of random user data, organized in JSON, for us to use freely.

The process of making an API call to that URL and then using that data to display something in our application is the `consumation` of that API.

Now, how do we go about doing this? Take the [RandomUser API](https://randomuser.me/api/) and follow this basic guide to get started quickly:

1. **Read the documentation**. It's important to first know how the API works (what are the endpoints, what kind of data does it deliver, etc.). Every decent API has some sort of online documentation. The format and location is not standard. Look for a "docs"/"documentation" link. Pay special attention to authentication, versioning and how data is passed (query string or body).
2. **Try out the most basic example** you can find in isolation. This usually means trying out the provided example, which the documentation provides. Remember to use Postman to test it out!
3. **Build up a library of Postman requests** for the API calls that you plan to use, they will be invaluable in debugging later.
4. **Start implementing the API** calls in your application. You would usually do this within a route inside of your backend application, or in the frontend after an event has happened.

Further materials to learn more about this:

- [What Is an API and Why Should I Use One?](https://medium.com/@TebbaVonMathenstien/what-is-an-api-and-why-should-i-use-one-863c3365726b)
- [API calls from Node.js](https://youtu.be/ZtLVbJk7KcM)

## 2. What is a templating engine?

So far all the servers that we have build were serving so-called **static** HTML. This means that the contents of the HTML did not change over time or based on the user.

With a `templating engine`, it's possible to create `dynamic` pages where parts of the content depend on the user that is viewing the page; the content changes depending on who the user is and what they're doing.

Take for example your Facebook account. Most likely the content you see will be different from the content I'll see in my account. The server takes a look at your login details and decides to inject the appropriate data into the frontend.

By using templating engines we can, for example, display the name of the user (that is logged in) on the page. Of course, one could add the HTML using client-side JavaScript, but this is not a good long-term solution. The code quickly becomes tangled and unmaintainable, because JavaScript code is intermixed with HTML.

Templating engines work by combining some data (usually in JSON format) and a static template file stored in the file system of your computer. The template created contains _placeholders_ where the data needs to be inserted. The process of combining the template and the data is often called _rendering_.

![Templating engines diagram](https://hackernoon.com/hn-images/1*XNuVdKSup2Gk9LjDNlsCYw.png)

The exact syntax and setup vary considerably, but the main components _data_, _template_ and _placeholders_ are found in every engine. In addition to replacing data, many templating engines support some form of `conditional expressions` and `loops/forEach` for dealing with arrays.

There are many implementations of templating engines available: Mustache, Pug (Jade), Handlebars, etc. In this course we will use [Handlebars](https://handlebarsjs.com/).

The syntax for placeholders (that will be replaced with actual data) in Handlebars is _double curly brackets_: `{{}}`. Let's look at a simple example:

Template `Name: {{firstName}} {{lastName}}`  
Data `{ "firstName": "John", "lastName": "Doe" }`  
Output `Name: John Doe`

You can find more examples in the documentation [here](https://handlebarsjs.com/).

To easily use handlebars in combination with Express, we will use a special package called `express-handlebars`. This package lets handlebars interact directly with the Express request handler and render content directly to the response object. You can find a basic example [here](https://www.npmjs.com/package/express-handlebars#basic-usage).

To read more about this, study the following materials:

- [Express + Handlebars Tutorial](https://www.youtube.com/watch?v=1srD3Mdvf50)
- [Overview of JavaScript Templating Engines](https://strongloop.com/strongblog/compare-javascript-templates-jade-mustache-dust/)
- [Javascript Templating Language](https://medium.com/@1sherlynn/javascript-templating-language-and-engine-mustache-js-with-node-and-express-f4c2530e73b2)
- [Express-handlebars](https://www.npmjs.com/package/express-handlebars)

## Finished?

Are you finished with going through the materials? High five! If you feel ready to get practical, click [here](./MAKEME.md).

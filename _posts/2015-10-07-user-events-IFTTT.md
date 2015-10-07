---
layout: post
title: How to create personalized events on IFTTT
---
###IFTTT
[IFTTT](https://ifttt.com/) is a nice simple web service that I'm learning to love,
at its core it works as an adapter for the API's of many web services.
One of the major limitations (along with the fact that you can't chain more than two events)
**was** the lack of official support for user-generated events.

All the API's calls (either the *IF* or the *THAT* side of a recipe) are published
within a channel.
[Twitter](https://ifttt.com/twitter/recipes) has a channel,[Reddit](https://ifttt.com/reddit/recipes) has a channel and [Facebook](https://ifttt.com/facebook/recipes) has one too.
What if I wanted my own channel?

###Maker Channel
The [Maker Channel](https://ifttt.com/maker) answers all of our questions.
It's not going to *our* channel but we don't need one anymore, what we need
is someone capable of firing and receiving a web request and act accordingly.

###How?
Once we're connected to the Maker channel we're provided with a secret-key, that
key is going to be used as an identifier for our requests.

If what we want is a trigger (*if-side*) we'll choose the Maker channel and when
prompted we'll provide a name for the event.

In order to trigger that event the only thing we need to do now is
a POST or GET request to:

```
https://maker.ifttt.com/trigger/{your-event}/with/key/{your-secret-key}
```

We can also pass a JSON with up to 3 parameters.

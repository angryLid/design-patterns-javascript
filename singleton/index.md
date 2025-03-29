Is everyone here? Okay, let's get started. 
Last month, we discussed the Decorator design pattern.  
We first learned about its core concepts and intent. 
Then, we explored how it works in real-world JavaScript applications by writing code line by line.

I hope it was helpful and gave you a deeper unstanding of decorators. 
Anyway, in today's salon, I will continue with this approach.
There are no slides, only JavaScript snippets written manually. 
Because this is my first time presenting a technical topic in English, I will try to speak as smoothly as possible. 
If you have any questions, please feel free to interrupt me and ask.

The first design pattern I'd like to talk about today, is the singleton.
Before that I prepared a question for you. In JavaScript, How many ways are there to create a plain object? one? two? All right, let me reveal the answer. 

As far as I know, there is at least 4

The first way, and the way we actually use in our daily work, is the object literal: one left curly brace and one right curly brace

```javascript
var obj = {}
```

The second way, is to initialize the object by the constructor. 

```javascript
var obj = new Object()
```

The third way, is to call the object function directly, without the new keyword. 

```javascript
var obj = Object()
```

The last way is to create an object using Object.prototype

```javascript
var obj = Object.create(Object.prototype)
```

Actually, we rarely use the latter three. You might have read those from the Internet

Okay, let's get back to our topic: the Singleton.

> Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.

There isn't even a true class concept in JavaScript.

In my opinion, the Singleton isn't a pattern but rather a language feature in JavaScript.

So every object created using the literal syntax can be considered a Singleton.

Of course, the class keyword, as well as coding styles from traditional OOP languages, was introduced with ES6, a standard that is now nearly 10 years old.

We're going to take a look at how that works.

We'll create a class, let's say, http service. Then we define a static property named instance, assigned to the result of calling new HttpService()

If we happen to be working with TypeScript, we can add private before the constructor method, like this:

```typescript
class HttpService {
    static instance = new HttpService()
    private construtor() {}
}

var httpService = HttpService.instance
```

What's more, in some cases, all you need to do is define the class, leaving the initialization and management to the framework.

```typescript
class HttpService {

}
```

Oh, I lost something. Now it is complete.

```typescript
@Autowired
class HttpService {

}
```
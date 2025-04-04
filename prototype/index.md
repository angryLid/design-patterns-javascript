Prototype is also known as Clone.

It's about creating new objects by copying existing ones.

In JavaScript, there's another concept called prototype. 
they are entirely different from each other. So Don't mix them up.


Imagine a simple `User` class:

```javascript
class User {
    constructor(name) {
        this.name = name
    }
}
```

We could add a `clone` method like this, which returns a new instance cloned by the current one.

```javascript
class User {
    constructor(name) {
        this.name = name
    }

    clone() {
        return new User(this.name)
    }
}
```


In the real-world JS applications, we rarely use this pattern. 

Since if an object is complex with file access or network connections, we cannot copy those resources.

Otherwise, only objects containing values can be copied.

However, we usually copy them by the following ways.

```javascript

var arr = []
var obj = {}

[...arr] // the spread syntax
{...obj}
arr.slice()
Object.assign({}, obj)

structuredClone(obj)
```

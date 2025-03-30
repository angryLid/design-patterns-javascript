The next pattern I'd like to share with you is the Builder pattern.

In most cases, a constructor is sufficient to create an object.

However, when initializing a complex object, the Builder pattern helps separate the construction process.

We can consider the FormData class as an example of a builder. When we instantiate it, no parameters are passed:

```javascript 
var formData = new FormData()
```

Values are provided using the `append` method:

```javascript 
formData.append('username', 'foo')
formData.append('password', 'bar')

```

Unfortunately, the browser doesn't support method chaining for append, as it returns void

So such code won't work.

```javascript 
formData
    .append('username', 'foo')
    .append('password', 'bar')
```

However, in some other programming languages, You might see a builder like this

```javascript 
FormDataBuilder()
    .setItem(1, 2)
    .setItem(3, 4)
    .build()
```

It's easy to implement. 

First, we can create a function called `FormDataBuilder` and define a variable `formData` inside.

This function returns an object

```javascript 
function FormDataBuilder() {
    var formData = new FormData()
    return {

    }
}
```

Then we implement two methods for this object.

One is `setItem`, which calls the append method and returns the object itself.

The other is `build`, which just simply returns the `formData` variable.

```javascript 
function FormDataBuilder() {
    var formData = new FormData()
    return {
        setItem(...args) {
            formData.append(args)
            return this
        },
        build() {
            return formData
        }
    }
}
```

Now these client code works.








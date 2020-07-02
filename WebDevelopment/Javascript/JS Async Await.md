# JS Async Await

We use async await, to tell JavaScript to wait for Code to be executed before continuing 

For example we can tell Javascript to wait for data to be fetched from an api before using the expected response.

````javascript
const get = async () => {
    setLoading(true)
    const resp = await fetch('https://jsonplaceholder.typicode.com/todos/1')
    const json = await resp.json()
    setTitle(json['title'])
    setLoading(false)
  }
````

In this case we don't deed to add `.then` to handle the response as we know, that JavaScript waits for the request to be finished before moving on to the next line of code.

We can only use await in an async function.
# JS Fetch

We use fetch to acess APIs via http Methods, sucha s GET, POST ...

Fetch returns a Promise which means, that we use `then` to acces its response

An example for using fetch can look like the following:

```javascript
function handleErrors(response) {
    if (!response.ok) {
        throw Error(response.statusText);
    }
    return response;
}
fetch("http://httpstat.us/500")
    .then(handleErrors)
    .then(response => console.log("ok") )
    .catch(error => console.log(error) );
```

In the example we declare a generic error handling function that can be reused for all of our fetches, this way we can just call `.then(handleErrors)` after the fetch before handling the response. the handleErrors function checks the responses statuscode to determine wheter the http request succeeded, the catch error handles errors concerning the promise, for example when there is no internet connection and no http request can be submitted.
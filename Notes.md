## Javascript Promises

- Why use promises: Instead of using a callback function in a function, we can use promises
- What is a promise: A promise is an object with a state - pending, fulfilled and rejected
- You do not have to query promise to figure out if it has been fulfilled/rejected - we can use then() (for fulfilled) or catch() (for rejected)
- Concept of chaining in javascript - do one function and then chain is with the next thing - example fetch(url).then(f1).catch(f2)
- using .then we can create a sequence of callbacks. a.then.then.then.catch - the last catch catches any error which happens in any of the then. a and all thens are functions which operate on previous returned value
- When we create a new Promise we also need to define resolve and reject - provide pathways on how you resolve and reject the Promise. Syntax:
  ```
  new Promise((resolve, reject) => {})
  ```
- Then in ES2017 or ES8, async/await was introduced as syntactic sugar to handle promises. So callbacks, promised and then async/await. Now we do not need to chain and we can use multiple awaits in an async function.
- use Promise.all to wait for multiple promised to resolve and then execute a code using .then:
  ```
  let promises = []
  for (let i = 0; i < 10; i++) {
    promises.push(push a promise here)
  }
  Promise.all(promises).
    then((results) => {
      for (let i = 0; i < results.length; i++) {
        // code here
      }
    })
  ```
- Application of Promises: when we want to make multiple concurrent requests to different APIs and wait until all requests are completed to operate on the response. Similarly if we want to run multiple async functions concurrently instead of running it sequentially. Initiating api calls concurrently can reduce overall time but may hit rate limit if any
- https://medium.com/@copperwall/implementing-promise-all-575a07db509a

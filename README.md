# cit281-lab8
## Part 1: Create lab file and initialize Node.js folder
`npm init` 
## Part 2: Install node-fetch package 
`npm install --save fastify node-fetch@2`
## Part 3: Add fastify starter code
```// #1 TODO: Declare fastify object from fastify, and execute```

```// #2 TODO: Declare fetch object from node-fetch```


```
fastify.get("/photos", (request, reply) => {
 
 // #3 TODO: Adapt the following code to attempt to retrieve all photos from JSONPlaceholder site using fetch, and handle returned Promise using: - two .then() chain methods, return 200 - single .catch() chain method, return 404
  reply
  .code(200)
  .header("Content-Type", "text/json; charset=utf-8")
  .send({ error: "", statusCode: 200, photos: [] });
});

fastify.get("/photos/:id", (request, reply) => {
  // #4 TODO:
  // Adapt the following code to attempt to retrieve
  // a single photo from JSONPlaceholder site
  // using fetch, and handle returned Promise using:
  // - single .then() chain method, return 200
  // - single .catch() chain method, return 404
  // You may also try to use Object.keys() to 
  // ensure JSONPlaceholder returns an object with
  // properties. An empty object returned from 
  // JSONPlaceholder means that the passed photo ID
  // was invalid. Your server would also return
  // a 404 status code for an invalid Photo ID.

  const { id = "" } = request.params;  
  reply
  .code(200)
  .header("Content-Type", "text/json; charset=utf-8")
  .send({ error: "", statusCode: 200, photo: {} });
});

// Start server and listen to requests using Fastify
const listenIP = "localhost";
const listenPort = 8080;
fastify.listen(listenPort, listenIP, (err, address) => {
  if (err) {
    console.log(err);
    process.exit(1);
  }
  console.log(`Server listening on ${address}`);
});
```

<img width="457" alt="Screenshot 2023-06-06 at 10 32 18 AM" src="https://github.com/mmathes2/cit281-lab8/assets/134009490/cf1ca01c-3765-446f-b6e4-13444552aacf">

## Part 4: Add fastify and node-fetch require statements

<img width="435" alt="Screenshot 2023-06-06 at 10 34 18 AM" src="https://github.com/mmathes2/cit281-lab8/assets/134009490/2128ba9c-cac6-4a39-b0f2-45cda395a75c">

## Part 5: Fetch JSONPlaceholder data

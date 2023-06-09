# Express js

Programing Languange: javascript
Status Learn: Not started
type: framework

# my note

installing progress

```jsx
$ mkdir myapp
$ cd myapp
```

```jsx
$ npm init
```

```jsx
$ npm install express --no-save
//without dependenciens
```

copy and paste this code !
entry point : `index.js`

```jsx
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
```

link for learn

[ExpressJS Tutorial](https://www.tutorialspoint.com/expressjs/index.htm)

[ExpressJS - Intro & Project Setup](https://www.youtube.com/watch?v=39znK--Yo1o&list=PL_cUvD4qzbkwp6pxx27pqgohrsP8v1Wj2)

npm recommended

```jsx
npm install nodemon
```
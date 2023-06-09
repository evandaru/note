# MERN STACK

Status Learn: Not started
type: framework

1. make this

```jsx
const express = require('express');

// express app
const app = express()

//get
app.get('/', (req, res) => {
    res.json({ pesan: "halo" })
})

// listen app
app.listen(4000, () => {
    console.log(' http://localhost:4000/')
})
```

1. make .env and install `npm install dotenv`
# Axios

> [!NOTE] GET All Data


```js
const { default: axios } = require("axios")

let link = 'https://script.google.com/macros/s/AKfycby4jY2BZR8kYwMPRNrUGraEYdloM-rFNaCRkD2M3t34jnKCcj_t5iUmpXzybEedeRW6Sg/exec'
axios.get(link)
    .then((data) => console.log(data.data))
```

> [!NOTE] GET Specific Data

```js
const { default: axios } = require("axios")

let link = 'https://script.google.com/macros/s/AKfycby4jY2BZR8kYwMPRNrUGraEYdloM-rFNaCRkD2M3t34jnKCcj_t5iUmpXzybEedeRW6Sg/exec'
axios.get(link)
    .then((data) => console.log(data.data.data[0]))
```

> [!NOTE] GET cuman data 'nama' ato 'id' etc

```js
axios.get(link)
  .then((response) => {
    const data = response.data.data;
    const names = data.map((item) => {
      return item.nama;
    });
    console.log(names);
  })
  .catch((error) => {
    console.error(error);
  });
```

> [!NOTE] Post Data

```js
axios.post(link, {
    id: "sapi",
    nama: "sapi",
    skill: "sapi",
    pekerjaan: "sapi",
})
    .then((data) => console.log(data.data.data.postData.contents))
```
> [!NOTE] GET Specific Data



---
Type: framework
Language: ☕ javaScrpit
---
# Vue Best practice

---
> [!NOTE] Fast link ⚡  
```shell
git clone https://github.com/evandaru/vue-route-ts.git
```
## 🔗 Routing
```bash
yarn add vue-router@4
```
📁 make `/router/index.ts`
```typescript
import { createRouter, createWebHistory, RouteRecordRaw } from 'vue-router';
import Home from '../views/HomeView.vue';
import form from '../views/form.vue';

const routes: Array<RouteRecordRaw> = [
  {
    path: '/',
    name: 'Home',
    component: Home,
  },
  {
    path: '/form',
    name: 'form',
    component: form,
  },
];

const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default router;
```
📁 Create in `/App.vue`
```typescript
<script setup lang="ts">
</script>

<template>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <RouterLink to="/form">form</RouterLink>
  </nav>
  <RouterView />
</template>
```
📁 Add in `/main.ts`
```typescript
import { createApp } from 'vue'
import './style.css'
import App from './App.vue'
import router from './router'


createApp(App).use(router).mount('#app')
```
---
## 🔗 Props
🚀 Definite in your components `/view/home.vue`
```typescript
<template>
    <div class="flex justify-center items-center">{{ title }}</div>
</template>
  
<script setup lang="ts">
defineProps<{
    title?: string
    likes?: number
}>()
</script>
```
🚀 kemudian panggil `App.vue`
```typescript
<template >
  <div class="flex flex-col justify-center items-center h-screen ">
    <nav class="flex flex-row gap-5">
      <RouterLink to="/">Home </RouterLink>
      <RouterLink to="/form"> form</RouterLink>
    </nav>
    <RouterView title="aku adalah ikan" />
  </div>
</template>
```
---


## 🔗 Looping
```typescript
<div v-for="item in data">
	{{ item.name }}
</div>
...
const data = [
	{
		name: 'ikan',
		skill: 'turu'
	},
...
]
```
---

## 🔗 Condition

## 🔗 Install tailwind in vue CLI
link Learn : [Link here]([https://larainfo.com/blogs/how-to-install-tailwind-css-in-vue-3](https://larainfo.com/blogs/how-to-install-tailwind-css-in-vue-3))
1.  `vue add tailwind`
2.  delete `postcss.config.js` in root directory
3.  `npx tailwindcss init -p`
4.  add in tailwind.config.js
```js
content: [
    "./src/**/*.{vue,js,ts,jsx,tsx}"
  ],
```
---

## 🔗 Rest api with google Script

> [!NOTE] Form.vue
```ts
<template>

    <div>

        <form @submit.prevent="submitForm">
            <div>
                <input class="border border-black" type="text" v-model="dataForm.nama">
            </div>
            <button>input</button>
        </form>
    </div>
</template>

<script setup lang="ts">
import axios from 'axios'
const dataForm = {

    nama: "",
}
const link = "/api?action=insert"
async function submitForm() {
    try {
        const form = await axios.post(link, dataForm)
        console.log(form)
    }
    catch (e) {
        alert(e)
    }
}
</script>
```

> [!NOTE] Rest Api
> Google script

```js
const muriddb = SpreadsheetApp.getActive();
const sheet = muriddb.getSheetByName("murid");
function doGet() {
  let data = [];
  const rlen = sheet.getLastRow();
  const clen = sheet.getLastColumn();
  const row = sheet.getRange(1, 1, rlen, clen).getValues();
  for (let i = 0; i < row.length; i++) {
    const dataRow = row[i];
    let record = {};
    for (let j = 0; j < clen; j++) {
      record[row[0][j]] = dataRow[j];
    }
    if (i > 0) {
      data.push(record)
    }
  }
  const response = {
    "data": data
  };
  return ContentService.createTextOutput(JSON.stringify(response)).setMimeType(ContentService.MimeType.JSON);

}

  

function doPost(request) {
  const action = request.parameter.action;
  const data = JSON.parse(request.postData.contents);
  const id = Utilities.getUuid();
  const createdAt = new Date(); // Get current timestamp
  sheet.appendRow([
    id,
    data.nama,
    createdAt // Use the createdAt variable here
  ]);
  let response = {
    "success": true,
    "message": "yey",
    "data": request
  };
    return ContentService
    .createTextOutput(JSON.stringify(response))
    .setMimeType(ContentService.MimeType.JSON)
    .setHeader("Access-Control-Allow-Origin", "*"); // Mengizinkan akses dari semua origin
}
```

## 🔗 Checkbox vue
``` js
<template>

    <form @submit.prevent="submitForm">

        <input placeholder="Nama" type="text" v-model="dataForm.nama" class="border border-black">

  

        <select v-model="dataForm.jenis_kelamin" name="jenis_kelamin" id="jenisKelamin">

            <option value="">Pilih Jenis Kelamin</option>

            <option value="Pria">Pria</option>

            <option value="Wanita">Wanita</option>

        </select>

  

        <input placeholder="Domisili" type="text" v-model="dataForm.domisili" class="border border-black">

  

        <input placeholder="Nomor WhatsApp" type="text" v-model="dataForm.no_wa" class="border border-black">

  

        <input placeholder="Usia" type="text" v-model="dataForm.usia" class="border border-black">

  

        <input placeholder="Program" type="text" v-model="dataForm.program" class="border border-black">

  

        <p>Pilih Hari:</p>

        <input type="checkbox" v-model="dataForm.hari" value="anu" id="checkboxAnu">

        <label for="checkboxAnu">Anu</label>

        <br>

        <input type="checkbox" v-model="dataForm.hari" value="ikan" id="checkboxIkan">

        <label for="checkboxIkan">Ikan</label>

        <br>

        <input type="checkbox" v-model="dataForm.hari" value="sapi" id="checkboxSapi">

        <label for="checkboxSapi">Sapi</label>

        <br>

  

        <input placeholder="Waktu" type="text" v-model="dataForm.waktu" class="border border-black">

  

        <input placeholder="Tingkat" type="text" v-model="dataForm.tingkat" class="border border-black">

  

        <textarea placeholder="Informasi" v-model="dataForm.informasi" class="border border-black"></textarea>

  

        <input placeholder="Info" type="text" v-model="dataForm.info" class="border border-black">

  

        <button type="submit">Submit</button>

    </form>

</template>

<script setup lang="ts">

import axios from 'axios'

import { ref } from 'vue'

  

const dataForm = ref({

    nama: "",

    jenis_kelamin: "",

    domisili: "",

    no_wa: "",

    usia: "",

    program: "",

    hari: [], // Ubah ke array untuk menyimpan nilai checkbox yang dipilih

    waktu: "",

    tingkat: "",

    informasi: "",

    info: ""

})

  

const link = "/api?action=insert"

  

async function submitForm() {

    try {

        const response = await axios.post(link, dataForm.value)

        alert(JSON.stringify(dataForm.value.hari))

        console.log(response)

    } catch (error) {

        alert(error)

    }

}

</script>
```




# Error
## 🐤 Pas Deploy
```ts
[vite]: Rollup failed to resolve import "/public/img/logo%20-%20footer.svg" from "/opt/build/repo/src/components/navbar.vue?vue&type=script&setup=true&lang.ts".

11:30:26 AM: This is most likely unintended because it can break your application at runtime.
```

> [!NOTE] Solved
> `img` dirubah jadi `v-img` 


## 🐤 Routing gk ke detek

add file `vercel.json`
```json
{

    "rewrites": [

        {

            "source": "/(.*)",

            "destination": "/"

        }

    ]

}
```

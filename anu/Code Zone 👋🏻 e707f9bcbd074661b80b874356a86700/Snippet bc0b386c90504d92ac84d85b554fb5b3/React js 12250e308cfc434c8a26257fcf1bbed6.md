# React js

Programing Languange: javascript
Status Learn: Done
type: framework

[Draf](React%20js%2012250e308cfc434c8a26257fcf1bbed6/Draf%2095a6b2e5447d46c79e4c14d92b95b70a.md)

## Apa itu `map` ?

map adalah membuat array baru

```jsx
const array1 = [1, 4, 9, 16];

//jadi setiap perulangan bakalan dikalikan angka 2
const map1 = array1.map(nilai => nilai * 2);

console.log(map1);
// Expected output: Array [2, 8, 18, 32]
```

catatan saya

```tsx
import { useState } from 'react';

const data = {
  nama: "fauzan",
  skill: "terbang",
  pp: "https://i.pinimg.com/564x/48/78/75/48787557d681ffcbd22e1c17e3d01c94.jpg"
}
const mahasiswa = [
  { name: "ikan", id: 1 },
  { name: "sapi", id: 2 },
  { name: "kambing", id: 3 },
  { name: "harimau", id: 4 },
];
const listAnu = mahasiswa.map(mahasiswa =>
  <li key={mahasiswa.id}>
    {mahasiswa.name}
  </li>
)
/* eslint-disable @typescript-eslint/no-explicit-any */
export default function App() {

  return (
    <>
      <div className="bg-slate-950 h-screen flex flex-col justify-center items-center">
        <div className="text-white bg-slate-800 px-6 py-3 rounded-lg flex flex-col gap-4">
          <Belajar text="list anu" />
          <ul>{listAnu}</ul>
          <Belajar text="if else biasa" />
          {data.nama == "fauzan" ?
            (<KondisiBenar />) :
            (<KondisiSalah />)}
          <Kotak children={
            <>
              <Pp image={data.pp} />
            </>
          } text={data.nama} />
          <Belajar text="if else agak beda" />
          {data.skill == "terbang" && (<KondisiBenar />)}
          
          <Button text="Click here 🚀" />
        </div>

      </div>
    </>
  )
}

function Pp(props) {
  const { image } = props
  return (
    <img className="w-20 h-20 rounded-full" src={image} alt="" />
  )
}
function Kotak(coba) {
  const { text, children } = coba
  return (
    <div className="text-white bg-slate-600 px-6 py-3 rounded text-4xl m-3 flex flex-row justify-center items-center gap-5">
      {children}
      {text}
    </div>
  )
}
function KondisiBenar() {
  return (
    <div className="bg-slate-300 text-black px-6 py-3">
      benar
    </div>
  )
}
function KondisiSalah() {
  return (
    <div className="bg-red-600 px-6 py-3">
      salah
    </div>
  )
}
function Belajar(props) {
  const { text } = props
  return (
    <h1 className="text-xl font-bold">{text}</h1>
  )
}

const [count, setCount] = useState(0);
function Button(props) {
  const { text } = props
  function Tombol1() {
    setCount(count + 1);
    // console.log(count)
    // alert("hayoo mending kamu turu")
  }
  return (
    <button onClick={Tombol1} className="bg-blue-500 px-6 py-3 text-white text-2xl rounded">
      {text} dipanggil berapa? {count}
    </button>
  )
}
```
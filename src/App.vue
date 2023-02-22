<!--fris code <script setup>
import { ref } from "vue";
const name = "Vue 3";
const counter = ref(0);
const increment  = () => {
  counter.value++;
};
const decrement = () => {
  counter.value--;
};
const reset = () => {
  counter.value = 0 ;
};
</script>

<template>
  <h1>Hola {{ name }}!</h1>
  <h2 :class="counter >= 0 ? 'positive' : 'negative'" > {{ counter }} </h2>

  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="reset" :disabled=" !counter ">Reset</button>
  <button @click="addEventListener" :disabled=" !counter ">Reset</button>

</template>

<style>
.positive{
  color: green;
}
.negative{
  color: red;
}
</style>-->

<!-- second code  <script setup>
const name = "Vue 3";
const arrayFrutas = [
  {
  name: "Manzana",
  price: "$1.00",
  description: "Una Manzana",
  stock: 0,
  },
  {
  name: "Pera",
  price: "$2.00",
  description: "Una Pera",
  stock: 10,
  },
  {
  name: "Naranja",
  price: "$3.00",
  description: "Una Naranja",
  stock: 20,
  },
];
</script>
<template>
  <h1>Hola {{ name }}!</h1>
  <table>
    <tr>
      <th scope="col">name</th>
      <th scope="col">price</th>
      <th scope="col">description</th>
      <th scope="col">stock</th>
    </tr>
    <td>
      <li v-for="(frutas, index) in arrayFrutas" :key="index">
      {{ frutas.name }}
    </li>
    </td>
    <td>
      <li v-for="(frutas, index) in arrayFrutas" :key="index">
      {{ frutas.price }}
    </li>
    </td>
    <td>
      <li v-for="(frutas, index) in arrayFrutas" :key="index">
      {{ frutas.description }}
    </li>
    </td>
    <td>
      <li v-for="(frutas, index) in arrayFrutas" :key="index">
      {{ frutas.stock }}
    </li>
    </td>
  </table>
</template>-->
<!--
<script setup>
const name = "Vue 3";
const arrayFrutas = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una Manzana",
    stock: 0,
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una Pera",
    stock: 10,
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una Naranja",
    stock: 20,
  },
];
</script>

<template>
  <ul>
      <template v-for="fruta in arrayFrutas" :key="fruta.name">
        <li v-if="fruta.stock > 0 ">

          {{ fruta.name }}
      </li>

    </template>
  </ul>
</template>
-->
<script setup>
import { ref } from 'vue';
const prices = ref(true);
const descriptions = ref(true);
const stocks = ref(true);
const arrayFrutas = ref([
{
    name: "Manzana",
    price: "$1.00",
    description: "Una Manzana",
    stock: 0,
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una Pera",
    stock: 10,
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una Naranja",
    stock: 20,
  }
]);
const arrayN = {
  name: "",
    price: "$",
    description: "",
    stock: 0,
}

const ocultarPrecio = ()=> {
  prices.value = true;
  console.log(prices.value);
}
const mostrarPrecio = ()=> {
  prices.value = false;
  console.log(prices.value);
}
const ocultarDescrcipcion = ()=> {
  descriptions.value = true;
  console.log(descriptions.value);
}
const mostrarDescripcion = ()=> {
  descriptions.value = false;
  console.log(descriptions.value);
}
const ocultarStock = ()=> {
  stocks.value = true;
  console.log(stocks.value);
}
const mostrarStock = ()=> {
  stocks.value = false ;
  console.log(stocks.value);
}

arrayFrutas.value.push({});
</script>
<template>
  <table class="table" style="position: relative; bottom: 200px; right: 200px;">
  <thead>
    <tr>
      <th scope="col">name</th>
      <th scope="col">price</th>
      <th scope="col">description</th>
      <th scope="col">stock</th>
    </tr>
  </thead>
  <tbody>
    <td>
      <tr scope="row">
        <li v-for="(frutas, index) in arrayFrutas" :key="index">
          {{ frutas.name }}
        </li>
      </tr>
    </td>
    <td>
      <tr scope="row">
        <li  v-show="prices == false"  v-for="(frutas, index) in arrayFrutas" :key="index">
          {{ frutas.price }}
        </li>
      </tr> 
    </td>
    <td>
      <tr scope="row">
        <li  v-show="descriptions == false" v-for="(frutas, index) in arrayFrutas" :key="index">
          {{ frutas.description }}
        </li>
      </tr>
    </td>
    <td>
      <tr scope="row">
        <li  v-show="stocks == false" v-for="(frutas, index) in arrayFrutas" :key="index">
          {{ frutas.stock }}
        </li>
      </tr>
    </td>
  </tbody>
</table>
  <form>
    <input type="tex" v-model="arrayFrutas.name" placeholder="name">
    <input type="tex" v-model="arrayFrutas.price" placeholder="price">
    <input type="tex" v-model="arrayFrutas.description" placeholder="description">
    <input type="number" v-model="arrayFrutas.stock" placeholder="stock">
  </form>
  <div>
    <button type="submit" style="margin-top: 150px;">Agregar Objeto</button>
    <button type="button" @click="ocultarPrecio" >Ocultar Precio</button>
    <button type="button" @click="mostrarPrecio">Mostrar Precio</button>
    <button type="button" @click="ocultarDescrcipcion">Ocultar Descripcion</button>
    <button type="button" @click="mostrarDescripcion">Mostrar Descripcion</button>
    <button type="button" @click="ocultarStock">Ocultar Stock</button>
    <button type="button" @click="mostrarStock">Mostrar Stock</button>
  </div>
</template>
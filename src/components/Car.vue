<template>
   <h1 style="color: blue;">Escribiendo Coche desde Car.vue</h1>
   <button @click="printMsg(msg)">Print</button>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Colores:
      <span v-for="(color, index) in colors" :key="index"><br />
         {{ index }}: {{ color }}
      </span>
   </p>
   <p>Precio: {{ price }} €</p>
   <p>Potencias:</p>
   <ul>
      <template v-for="(power, index) in powers" :key="index">
         <li v-if="power < 450">Urbana: {{ power }} CV</li>
         <li v-else-if="power == 500">Híbrido: {{ power }} CV</li>
         <li v-else>Carretera: {{ power }} CV</li>
      </template>
   </ul>
   <p v-if="price > (1000 - proce)" style="color: red;"> No se puede subir más el precio.</p>
   <button @click="priceUp()" v-if="price < (1000 - proce)">Subir precio {{ proce }}</button>
   <p v-if="price < proce" style="color: red;"> No se puede bajar más el precio.</p>
   <button @click="priceDown()" v-if="price > proce">Bajar precio {{ proce }}</button>
   <p>{{ mensaje.title }} - {{ mensaje.text }}</p>

   <Wheel name="coche" :num=4 :printMsg="printMsg" />
</template>

<script>
import Wheel from './Wheel.vue';
import { ref } from "vue";

export default {
   props:
   {
      printMsg: Function
   },
   setup() {
      const msg = "Car.vue";
      const brand = "BMW";
      const model = "X5";
      const colors = ["Red", "Blue", "Green"];
      let price = ref(499);
      let proce = ref(100);
      const powers = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000];
      const mensaje = {
         title: "Das Auto",
         text: "Wolksvagen"
      };

      function priceUp() {
         console.log("Subiendo precio...")
         price.value += 100;
      };

      function priceDown() {
         console.log("Bajando precio...")
         if (price.value > proce.value) {
            price.value -= proce.value;
         }
      };

      return { brand, model, colors, price, proce, powers, mensaje, priceUp, priceDown, msg };
   },
   components: { Wheel }
};
</script>
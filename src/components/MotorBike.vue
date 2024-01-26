<template>
   <div class="container">
      <h1 class="title">Escribiendo Motocicleta desde MotorBike.vue</h1>
      <button @click="printMsg(msg)">Print</button>
      <p>Marca: {{ brand }}</p>
      <p>Modelo: {{ model }}</p>
      <p>Color: {{ color[1] }}</p>
      <p>Precio: {{ price }} €</p>
      <p>Potencia: {{ power }} CV:
         <span v-if="power < 200">Urbana</span>
         <span v-else-if="power < 300">Híbrido</span>
         <span v-else>Carretera</span>
      </p>
      <p v-if="power >= (400 - cant)" style="color: red;"> No se puede subir más la potencia.</p>
      <button @click="priceUp()" v-if="power < (400 - cant)">Subir potencia {{ cant }}</button>
      <p v-if="power <= cant" style="color: red;"> No se puede bajar más la potencia.</p>
      <button @click="priceDown()" v-if="power > cant">Bajar potencia {{ cant }}</button>

      <Wheel name="motocicleta" :num=2 :fem=true :printMsg="printMsg" />
   </div>
</template>

<script>
import { ref } from "vue";
import Wheel from './Wheel.vue';
export default {
   props:
   {
      printMsg: Function
   },
   setup() {
      const msg = "MotorBike.vue";
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const price = 1500;
      let power = ref(100);
      let cant = ref(10);

      function priceUp() {
         console.log("Subiendo potencia...")
         power.value += cant.value;
      };

      function priceDown() {
         console.log("Bajando potencia...")
         power.value -= cant.value;
      };

      return { brand, model, color, price, power, cant, priceUp, priceDown, msg };
   },
   components: { Wheel }
}
</script>

<style lang="scss" scoped>
.container {
   background-color: rgb(56, 53, 31);
   .title {
      color: rgb(27, 162, 36);
   }
}
</style>
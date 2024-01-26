<template>
   <div class="container">
      <h1 class="title">Escribiendo Avión desde Plane.vue</h1>
      <button @click="printMsg(msg)">Print</button>
      <p>Marca: {{ brand }}</p>
      <p>Modelo: {{ model }}</p>
      <p>Color: {{ color[1] }}</p>
      <p>Altitud máxima: {{ height }} m</p>

      <p v-if="height >= (120000 - heightstep)" style="color: red;"> No se puede subir más la altura.</p>
      <button @click="priceUp()" v-if="height < (120000 - heightstep)">Subir altura {{ heightstep }}</button>
      <p v-if="height <= heightstep" style="color: red;"> No se puede bajar más la altura.</p>
      <button @click="priceDown()" v-if="height > heightstep">Bajar altura {{ heightstep }}</button>

      <Wheel name="avion" :num=16 :printMsg="printMsg" />
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
      const msg = "Plane.vue";
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      let height = ref(100000);
      let heightstep = ref(2000);

      function priceUp() {
         console.log("Subiendo altura...")
         height.value += heightstep.value;
      };

      function priceDown() {
         console.log("Bajando altura...")
         if (height.value > heightstep.value) {
            height.value -= heightstep.value;
         }
      };

      return { brand, model, color, height, heightstep, priceUp, priceDown, msg };
   },
   components: { Wheel }
};
</script>

<style lang="scss" scoped>
.container {
   background-color: rgb(50, 43, 43);

   .title {
      color: pink;
   }
}
</style>
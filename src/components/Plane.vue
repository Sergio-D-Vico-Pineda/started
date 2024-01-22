<template>
   <h1 style="color: purple;">Escribiendo Avión desde Plane.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Altitud máxima: {{ height }} m</p>

   <p v-if="height >= (120000 - heightstep)" style="color: red;"> No se puede subir más el precio.</p>
   <button @click="priceUp()" v-if="height < (120000 - heightstep)">Subir precio {{ heightstep }}</button>
   <p v-if="height <= heightstep" style="color: red;"> No se puede bajar más el precio.</p>
   <button @click="priceDown()" v-if="height > heightstep">Bajar precio {{ heightstep }}</button>

   <Wheel name="avion" num="16" />
</template>

<script>
import { ref } from "vue";
import Wheel from './Wheel.vue';

export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      let height = ref(100000);
      let heightstep = ref(2000);

      function priceUp() {
         console.log("Subiendo precio...")
         height.value += heightstep.value;
      };

      function priceDown() {
         console.log("Bajando precio...")
         if (height.value > heightstep.value) {
            height.value -= heightstep.value;
         }
      };

      return { brand, model, color, height, heightstep, priceUp, priceDown };
   },
   components: { Wheel }
};
</script>
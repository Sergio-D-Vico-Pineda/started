<template>
   <h1 style="color: red;">Escribiendo Motocicleta desde MotorBike.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Precio: {{ price }} €</p>
   <p>Potencia: {{ power }} CV:
      <span v-if="power < 200">Urbana</span>
      <span v-else-if="power < 300">Híbrido</span>
      <span v-else>Carretera</span>
   </p>
   <button @click="priceUp()" v-if="true">Subir potencia {{ cant }}</button>
   <button @click="priceDown()" v-if="true">Bajar potencia {{ cant }}</button>

   <Wheel name="motocicleta" num="2" fem="true" />
</template>

<script>
import { ref } from "vue";
import Wheel from './Wheel.vue';
export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const price = 100000;
      let power = ref(100);
      let cant = ref(10);

      function priceUp() {
         console.log("Subiendo precio...")
         power.value += cant.value;
      };

      function priceDown() {
         console.log("Bajando precio...")
         power.value -= cant.value;
      };

      return { brand, model, color, price, power, cant, priceUp, priceDown };
   },
   components: { Wheel }
}
</script>
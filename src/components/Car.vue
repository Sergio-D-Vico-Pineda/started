<template>
   <h1 style="color: blue;">Escribiendo Coche desde Car.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Colores:
      <span v-for="(color, index) in colors" :key="index"><br />
         {{ index }}: {{ color }}
      </span>
   </p>
   <p>Precio: {{ price }} €</p>
   <p>Potencia urbanas menor a 450 CV</p>
   <ul>
      <template v-for="(power, index) in powers" :key="index">
         <li v-if="power < 450">Urbana: {{ power }} CV</li>
         <li v-else-if="power == 500">Híbrido: {{ power }} CV</li>
         <li v-else>Carretera: {{ power }} CV</li>
      </template>
   </ul>
   <p>{{ mensaje.title }} - {{ mensaje.text }}</p>

   <Wheel name="coche" num="4" />
</template>

<script>
import Wheel from './Wheel.vue';

export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const colors = ["Red", "Blue", "Green"];
      const price = 243252;
      const powers = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000];
      const mensaje = {
         title: "Das Auto",
         text: "Wolksvagen"
      };
      return { brand, model, colors, price, powers, mensaje };
   },
   components: { Wheel }
};
</script>
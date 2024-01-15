<template>
   <h1 style="color: purple;">Escribiendo Avión desde Plane.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Altitud máxima: {{ height }} €</p>

   <Wheel name="avion" num="16" />
</template>

<script>
import Wheel from './Wheel.vue';

export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const height = 100000;

      return { brand, model, color, height };
   },
   components: { Wheel }
};
</script>
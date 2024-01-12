<template>
   <h1 style="color: purple;">Escribiendo Avión desde Plane.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Altitud máxima: {{ height }} €</p>
   <WheelPlane />
</template>

<script>
import WheelPlane from './WheelPlane.vue';

export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const height = 100000;

      return { brand, model, color, height };
   },
   components: { WheelPlane }
};
</script>
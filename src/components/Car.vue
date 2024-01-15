<template>
   <h1 style="color: blue;">Escribiendo Coche desde Car.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ colors[1] }}</p>
   <p>Precio: {{ price }} €</p>
   <p>Potencia: {{ powers[1] }} CV</p>
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
         title: "El mejor vehiculo",
         text: "Richard Stallman"
      };
      return { brand, model, colors, price, powers, mensaje };
   },
   components: { Wheel }
};
</script>
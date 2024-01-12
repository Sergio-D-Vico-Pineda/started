<template>
   <h1 style="color: blue;">Escribiendo Coche desde Car.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Precio: {{ price }} €</p>
   <p>Potencia: {{ power }} CV</p>
   <p>{{ mensaje.title }} - {{ mensaje.text }}</p>

   <WheelCar />
</template>

<script>
import WheelCar from './WheelCar.vue';

WheelCar.setup = () => {
   const num = 5;
   return { num };
};

export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const price = 100000;
      const power = 300;
      const mensaje = {
         title: "Coche",
         text: "muy caro"
      };
      return { brand, model, color, price, power, mensaje };
   },
   components: { WheelCar }
};
</script>
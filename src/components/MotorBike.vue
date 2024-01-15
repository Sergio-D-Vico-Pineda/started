<template>
   <h1 style="color: red;">Escribiendo Motocicleta desde MotorBike.vue</h1>
   <p>Marca: {{ brand }}</p>
   <p>Modelo: {{ model }}</p>
   <p>Color: {{ color[1] }}</p>
   <p>Precio: {{ price }} €</p>
   <p>Potencia: {{ power }} CV</p>
   
   <Wheel name="motocicleta" num="2" fem="true" />
</template>

<script>
import Wheel from './Wheel.vue';
export default {
   setup() {
      const brand = "BMW";
      const model = "X5";
      const color = ["Red", "Blue", "Green"];
      const price = 100000;
      const power = 100;

      return { brand, model, color, price, power };
   },
   components: { Wheel }
}
</script>
<template>
   <!--    <h1>Vue JS</h1>
   <p>Hola mundo</p> -->
   <marquee scrollamount="100" behavior="alternate">Hola</marquee>
   <div style="display: flex;gap:20px">
      <div>
         <Car />
      </div>
      <div>
         <Plane />
      </div>
      <div>
         <MotorBike />
      </div>
   </div>
</template>

<script>
import Car from './components/Car.vue';
import Plane from './components/Plane.vue';
import MotorBike from './components/MotorBike.vue';

export default {
   components: {
      Car,
      Plane,
      MotorBike
   }
};

</script>

<style>
* {
   box-sizing: border-box;
}

body {
   background-color: rgb(30, 28, 28);
   color: white;
}
</style>

<!-- <template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
 -->
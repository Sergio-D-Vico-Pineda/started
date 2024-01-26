<template>
   <!--    <h1>Vue JS</h1>
   <p>Hola mundo</p> -->
   <marquee>
      <button @click="printMsg(msg)">Hazme click y mira la consola</button>
   </marquee>
   <div style="display: flex;gap:20px">
      <div>
         <Car :printMsg="printMsg" />
      </div>
      <div>
         <Plane :printMsg="printMsg" />
      </div>
      <div>
         <MotorBike :printMsg="printMsg" />
      </div>
   </div>
</template>

<script>
import Car from './components/Car.vue';
import Plane from './components/Plane.vue';
import MotorBike from './components/MotorBike.vue';

export default {
   setup() {
      let msg = "App.vue";
      let printMsg = (msg) => {
         alert(`Este mensaje se ha ejecutado en ${msg}`);
      };

      return { msg, printMsg };
   },

   components: {
      Car,
      Plane,
      MotorBike
   }
};

</script>

<style lang="scss">
* {
   box-sizing: border-box;
}

body {
   background-color: rgb(30, 28, 28);
   color: white;

   .title {
      color: white;
   }
}

.container {
   padding: 0px 10px 10px;
   border-radius: 20px;
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
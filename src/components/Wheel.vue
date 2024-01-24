<template>
   <h2 v-if="fem">Ruedas de la {{ name }}</h2>
   <h2 v-else>Ruedas del {{ name }}</h2>
   <p v-if="num > 1">Tiene {{ num }} ruedas</p>
   <p v-else-if="num == 1">Tiene {{ num }} rueda</p>
   <button @click="printMsg(msg)">Ruedas print</button>
</template>

<script>
export default {
   props:
   {
      printMsg: Function,
      name: String,
      num: Number,
      fem: Boolean
   },
   setup() {
      let msg = "Wheel.vue";
      return { msg };
   }
}
</script>
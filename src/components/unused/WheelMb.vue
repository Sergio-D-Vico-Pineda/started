<template>
   <h2>Ruedas de la motocicleta</h2>
   <p>Tiene {{ num }} ruedas</p>
</template>

<script>
export default {
   setup() {
      const num = 2;
      return { num };
   }
}
</script>
<template>
   <h2>Ruedas del coche</h2>
   <p>Tiene {{ num }} ruedas</p>
</template>

<script>
export default {
   setup() {
      const num = 4;
      return { num };
   }
}
</script>
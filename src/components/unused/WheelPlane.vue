<template>
   <h2>Ruedas del avión</h2>
   <p>Tiene {{ num }} ruedas</p>

</template>

<script>
export default {
   setup() {
      const num = 6;
      return { num };
   }
}
</script>
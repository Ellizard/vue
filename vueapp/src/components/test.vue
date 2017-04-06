<template>
  <div class="test">
    <h1>
      {{ title }}
    </h1>
  </div>
</template>



<script>
  export default {
    name: 'test',
    data() {
      return {
        title: 'test hello',
        user: {
          name: 'John',
          lastname: 'Doe',

        }
      }
    }
  }
</script>


<style scoped>

</style>
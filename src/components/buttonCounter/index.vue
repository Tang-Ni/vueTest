<template>
  <button v-on:click="increments">{{counter}}</button>
</template>
<script>
  export default {
    data() {
      return {
        counter: 0
      }
      },
      methods: {
        increments: function() {
          this.counter += 1
          this.$emit('increment')
        }
      }
  }
</script>

<template>
  <div>
  <p>{{ total }}</p>
  <button-counter v-on:increment="incrementTotal"></button-counter>
  <button-counter v-on:increment="incrementTotal"></button-counter>
</div>
</template>

<script>
import buttonCounter from './components/buttonCounter/index.vue'
export default{
components:{
buttonCounter
},

  data () {
    return{
    total: 0
    }
  },
  methods: {
    incrementTotal: function () {
      this.total += 1
    }
  }
}
</script>

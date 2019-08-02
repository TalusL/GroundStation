<template>
  <div id="wrapper" >
    <canvas id="canvas"></canvas>
  </div>
</template>

<script>
  import Model from '../util/model'
  export default {
    name: 'landing-page',
    methods: {
    },
    mounted () {
      this.model = new Model(document.getElementById('wrapper'), document.getElementById('canvas'))
      debugger
    }
  }
</script>

<style>
</style>

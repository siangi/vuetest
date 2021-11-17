<template>
  <div class="Location">
    <h1>{{name}}</h1>
    <p>{{adress}}</p>
    <p>{{description}}</p>
    <image src="{{imageUrl}}"/>
  </div>
</template>

<script>
export default {
  name: 'Location',
  props: {
    name: String,
    adress: String,
    description: String,
    imageUrl: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

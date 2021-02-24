<template>
  <div class="hello">
    <p>{{ten}}</p>
     <slot name="test1"></slot>
    <p>ass</p>
  </div>
</template>

<script>
export default {
  name: 'test',
  props: {
    ten: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

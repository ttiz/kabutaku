<template>
  <div id="app">
    <input type="number" v-model.number="price">
    <p>{{ price }}</p>

  </div>
</template>

<script>
export default {
  data() {
    return {
      price: '',
    }
  },
}
</script>
<template>
  <div id="app">
    <div class="input-container">
      <label for="price" class="input-label">Price</label>
    <input type="number" v-model.number="price">
    </div>
    <div class="input-container">
      <label for="eps" class="input-label">Earnings Per Share (EPS)</label>
    <input type="number" v-model.number="eps">
    </div>
    <div class="input-container">
      <label for="per" class="input-label">Price-to-Earnings ratio (PER)</label>
    <input type="number" v-model.number="per">
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      price: '',
      eps:'',
      per:'',
    }
  },
  watch: {
    price() {
      this.per = this.price/this.eps;
    },
    eps() {
      this.per = this.price/this.eps;
    }
  }
}
</script>

<style scoped>
.input-container {
  margin-bottom: 10px;
}

.input-label {
  display: inline-block;
  margin-bottom: 5px;
}

.input-field {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
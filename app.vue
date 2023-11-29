<template>


  <div id="app">
    <div class="columns is-mobile  is-variable is-6">
      <div class="column is-half">
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
      <div class="input-container">
        <label for="per" class="input-label">Target Price-to-Earnings ratio (PER)</label>
        <input type="number" v-model.number="target_per">
      </div>
      </div>

      <div class="column is-half">
      <label for="per" class="input-label">Target Price</label>
      {{target_price}}
      </div>
  </div>
  </div>
</template>

<script>
import 'bulma/css/bulma.css';
export default {
  data() {
    return {
      price: '',
      eps:'',
      per:'',
      target_per:'',
      target_price:'',
    }
  },
  watch: {
    price() {
      this.per = this.price/this.eps;
    },
    eps() {
      this.target_price = this.target_per * this.eps;
      this.per = this.price/this.eps;
    },
    per(){
      // this.eps = this.price/this.per;
    },
    target_per(){
      this.target_price = this.target_per * this.eps;



    }

  }
}
</script>

<style scoped>
.columns{
  padding: 10px;
}

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
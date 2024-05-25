<template>
  <div id="app">
    <h1>Skincare Store</h1>
    <Slot v-if="purchaseMessage">
      {{ purchaseMessage }}
    </Slot>
    <Slot v-else />
    <Product @purchase-success="handlePurchaseSuccess" />
  </div>
</template>

<script>
import Product from './components/Product.vue'
import Slot from './components/Slot.vue'

export default {
  name: 'App',
  components: {
    Product,
    Slot
  },
  data() {
    return {
      purchaseMessage: ''
    }
  },
  methods: {
    handlePurchaseSuccess(productName) {
      this.purchaseMessage = `Pembelian ${productName} Berhasil!`;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Arial', sans-serif;
  text-align: center;
  margin-top: 20px;
  padding: 20px;
  background-color: #f9f9f93c;
}

h1 {
  color: #333;
  margin-bottom: 20px;
}
</style>

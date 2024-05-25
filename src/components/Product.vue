<template>
    <div class="product-list">
      <div v-for="product in products" :key="product.id" class="product">
        <h2>{{ product.name }}</h2>
        <p>Harga: Rp {{ product.price.toLocaleString('id-ID') }}</p>
        <Emit @purchase-success="handlePurchaseSuccess(product.name)"></Emit>
      </div>
    </div>
  </template>
  
  <script>
  import Emit from './Emit.vue';
  
  export default {
    name: 'Product',
    components: {
      Emit
    },
    data() {
      return {
        products: [
          { id: 1, name: 'Moisturizer', price: 150000 },
          { id: 2, name: 'Cleanser', price: 80000 },
          { id: 3, name: 'Sunscreen', price: 120000 }
        ]
      }
    },
    methods: {
      handlePurchaseSuccess(productName) {
        this.$emit('purchase-success', productName);
      }
    }
  }
  </script>
  
  <style scoped>
  .product-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 20px;
    margin-top: 20px;
  }
  
  .product {
    background-color: rgba(255, 255, 255, 0.324);
    border: 1px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 20px;
    width: 250px;
    text-align: center;
  }
  
  h2 {
    color: #42b983;
    font-size: 24px;
    margin-bottom: 10px;
  }
  
  p {
    color: #666;
    font-size: 18px;
    margin-bottom: 20px;
  }
  </style>
  
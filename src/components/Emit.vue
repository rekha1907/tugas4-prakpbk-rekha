<template>
    <button @click="emitPurchase">Beli Produk</button>
  </template>
  
  <script>
  export default {
    name: 'Emit',
    methods: {
      emitPurchase() {
        this.$emit('purchase-success');
      }
    }
  }
  </script>
  
  <style scoped>
  button {
    background-color: #42b983;
    color: white;
    border: none;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin-top: 10px;
    cursor: pointer;
    border-radius: 4px;
    transition: background-color 0.3s ease;
  }
  
  button:hover {
    background-color: #369f75;
  }
  </style>
  
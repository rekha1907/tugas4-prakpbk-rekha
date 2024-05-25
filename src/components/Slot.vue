<template>
    <div class="message">
      <slot>Silahkan beli produk di sini</slot>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Slot'
  }
  </script>
  
  <style scoped>
  .message {
    margin-top: 20px;
    font-size: 18px;
    color: #333;
    background-color: #e0ffe02c;
    padding: 10px;
    border-radius: 4px;
    border: 1px solid #42b983;
  }
  </style>
  
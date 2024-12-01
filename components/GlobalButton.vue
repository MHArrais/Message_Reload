<template>
    <button class="custom-button">
      <slot>Click Me</slot>
    </button>
  </template>
  
  <script>
  export default {
    name: "CustomButton",
  };
  </script>
  
  <style scoped>
  .custom-button {
    background-color: #4caf50; /* Verde */
    color: white;
    border: none;
    border-radius: 8px;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.2s ease;
  }
  
  .custom-button:hover {
    background-color: #45a049;
  }
  
  .custom-button:active {
    transform: scale(0.98);
  }
  </style>
  
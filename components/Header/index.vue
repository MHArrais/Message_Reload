<template>
    <header class="flex justify-between items-center p-4 bg-gray-800 text-white">
      <!-- Botão de Sair no canto direito -->
      <button @click="Sair" class="bg-red-500 text-white px-4 py-2 rounded-md hover:bg-red-600">
        Sair
      </button>
  
      <!-- Logo no centro -->
      <div class="absolute left-1/2 transform -translate-x-1/2">
        <img src="../../assets/LUA.jpeg" alt="Logo" class="h-8" />
      </div>
    </header>
  </template>
  
  <script>
  export default {
    methods: {
      Sair() {
        // Redireciona para a página de Login
        this.$router.push("/Login");
      },
    },
  };
  </script>


  
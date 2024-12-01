<template>
  <!-- component -->
  <div class="bg-black flex justify-center items-center h-screen">
    <!-- Left: Image -->
    <div class="w-1/2 h-screen hidden lg:block">
      <img
        src="../../assets/LOGO.jpg"
        alt="Placeholder Image"
        class="object-cover w-full h-full"
      />
    </div>
    <!-- Right: Login Form -->
    <div class="lg:p-36 md:p-52 sm:20 p-8 w-full lg:w-1/2">
      <h1 class="text-2xl font-semibold mb-4 neon-effect">Login</h1>

      <!-- e-mail Input -->
      <div class="mb-4">
        <label for="e-mail" class="block text-white">E-mail</label>
        <input
          v-model="Email"
          type="text"
          id="e-mail"
          name="e-mail"
          class="w-full border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:border-blue-500"
          autocomplete="off"
        />
      </div>
      <!-- Password Input -->
      <div class="mb-4">
        <label for="password" class="block text-white">Password</label>
        <input
          v-model="Senha"
          type="password"
          id="password"
          name="password"
          class="w-full border border-gray-300 rounded-md py-2 px-3 focus:outline-none focus:border-blue-500"
          autocomplete="off"
        />
      </div>
      <!-- Remember Me Checkbox -->
      <div class="mb-4 flex items-center">
        <input
          type="checkbox"
          id="remember"
          name="remember"
          class="text-blue-500"
        />
        <label for="remember" class="text-white ml-2 neon-effect">Remember Me</label>
      </div>
      <!-- Forgot Password Link -->
      <div class="mb-6 text-blue-500">
        <a href="#" class="hover:underline neon-effect">Forgot Password?</a>
      </div>
      <!-- Login Button -->
      <button
        @click="Entrar"
        type="submit"
        class="bg-blue-500 hover:bg-blue-600 text-white font-semibold rounded-md py-2 px-4 w-full"
      >
        Login
      </button>

      <!-- Sign up  Link -->
      <div class="mt-6 text-blue-500 text-center">
        <a href="#" class="hover:underline neon-effect">Sign up Here</a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.neon-effect {
  color: white; /* Cor do texto padrão */
  text-shadow: 0 0 5px #00f, 0 0 10px #00f, 0 0 15px #00f, 0 0 20px #00f; /* Efeito neon azul */
  transition: text-shadow 0.3s ease-in-out; /* Suaviza a transição do efeito */
}


</style>

<script>
export default {
  data() {
    return {
      Email: "",
      Senha: "",
      Usuario: "admin",
      Password: "1234",
      erro: "", // Para armazenar mensagens de erro
      };
  },
  methods: {
    Entrar() {
    if (!this.Email || !this.Senha) {
      this.erro = "Por favor, preencha todos os campos.";
      return;
    }

    if (this.Email === this.Usuario && this.Senha === this.Password) {
      this.$router.push("/home");
    } else {
      this.erro = "Credenciais inválidas. Tente novamente.";
    }
  },
  },
};
</script>

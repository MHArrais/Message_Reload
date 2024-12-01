<template>
    <div class="flex flex-col justify-center items-center" style="background-color: #373B3E; height: 100vh;">
        <div
            class="mx-auto flex w-full mt-20 flex-col justify-center px-5 pt-0 md:h-[unset] md:max-w-[80%] lg:h-[60vh] lg:max-w-[80%] lg:px-6 xl:pl-0 ">
            <div class="relative flex w-full flex-col pt-[20px] md:pt-0"> 
                <div class="mx-auto flex min-h-[25vh] w-full max-w-[1000px] flex-col xl:min-h-[35vh]"> 
                    <div class="mx-auto flex w-full flex-col flex mb-auto">
                        <div class="mb-2.5 flex w-full items-center text-center">
                            <div
                                class="mr-5 flex h-[40px] min-h-[40px] min-w-[40px] items-center justify-center rounded-full border border-zinc-200 bg-transparent dark:border-transparent dark:bg-white">
                                <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24"
                                    aria-hidden="true" class="h-4 w-4" height="1em" width="1em"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd"
                                        d="M7.5 6a4.5 4.5 0 1 1 9 0 4.5 4.5 0 0 1-9 0ZM3.751 20.105a8.25 8.25 0 0 1 16.498 0 .75.75 0 0 1-.437.695A18.683 18.683 0 0 1 12 22.5c-2.786 0-5.433-.608-7.812-1.7a.75.75 0 0 1-.437-.695Z"
                                        clip-rule="evenodd"></path>
                                </svg></div>
                            <div class="flex w-full">
                                <div
                                    class="me-2.5 flex w-full rounded-lg border border-zinc-200 bg-white/10 p-5 backdrop-blur-xl dark:border-white/10 dark:bg-zinc-950">
                                    <p v-if="advice"
                                        class="text-sm font-medium leading-6 text-white dark:text-white md:text-base md:leading-[26px]">
                                        {{ advice }}
                                    </p>
                                </div>
                  
                                  <button @click="Buscar">
                                    <div
                                    class="flex w-[70px] cursor-pointer items-center justify-center rounded-lg border border-zinc-200 bg-white/10 p-5 backdrop-blur-xl dark:border-white/10 dark:bg-zinc-950">
                                    <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 20 20"
                                        aria-hidden="true" class="h-[20px] w-[20px] text-zinc-950 dark:text-white"
                                        height="1em" width="1em" xmlns="http://www.w3.org/2000/svg">
                                        <path
                                            d="m5.433 13.917 1.262-3.155A4 4 0 0 1 7.58 9.42l6.92-6.918a2.121 2.121 0 0 1 3 3l-6.92 6.918c-.383.383-.84.685-1.343.886l-3.154 1.262a.5.5 0 0 1-.65-.65Z">
                                        </path>
                                        <path
                                            d="M3.5 5.75c0-.69.56-1.25 1.25-1.25H10A.75.75 0 0 0 10 3H4.75A2.75 2.75 0 0 0 2 5.75v9.5A2.75 2.75 0 0 0 4.75 18h9.5A2.75 2.75 0 0 0 17 15.25V10a.75.75 0 0 0-1.5 0v5.25c0 .69-.56 1.25-1.25 1.25h-9.5c-.69 0-1.25-.56-1.25-1.25v-9.5Z">
                                        </path>
                                    </svg>
                                  </div>


                                  </button>



                            </div>
                        </div>
                        <div class="flex w-full">
                            <div
                                class="mr-5 flex h-10 min-h-[40px] min-w-[40px] items-center justify-center rounded-full bg-zinc-950 dark:border dark:border-zinc-800">
                                <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24"
                                    aria-hidden="true" class="h-4 w-4 text-white" height="1em" width="1em"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd"
                                        d="M9 4.5a.75.75 0 0 1 .721.544l.813 2.846a3.75 3.75 0 0 0 2.576 2.576l2.846.813a.75.75 0 0 1 0 1.442l-2.846.813a3.75 3.75 0 0 0-2.576 2.576l-.813 2.846a.75.75 0 0 1-1.442 0l-.813-2.846a3.75 3.75 0 0 0-2.576-2.576l-2.846-.813a.75.75 0 0 1 0-1.442l2.846-.813A3.75 3.75 0 0 0 7.466 7.89l.813-2.846A.75.75 0 0 1 9 4.5ZM18 1.5a.75.75 0 0 1 .728.568l.258 1.036c.236.94.97 1.674 1.91 1.91l1.036.258a.75.75 0 0 1 0 1.456l-1.036.258c-.94.236-1.674.97-1.91 1.91l-.258 1.036a.75.75 0 0 1-1.456 0l-.258-1.036a2.625 2.625 0 0 0-1.91-1.91l-1.036-.258a.75.75 0 0 1 0-1.456l1.036-.258a2.625 2.625 0 0 0 1.91-1.91l.258-1.036A.75.75 0 0 1 18 1.5ZM16.5 15a.75.75 0 0 1 .712.513l.394 1.183c.15.447.5.799.948.948l1.183.395a.75.75 0 0 1 0 1.422l-1.183.395c-.447.15-.799.5-.948.948l-.395 1.183a.75.75 0 0 1-1.422 0l-.395-1.183a1.5 1.5 0 0 0-.948-.948l-1.183-.395a.75.75 0 0 1 0-1.422l1.183-.395c.447-.15.799-.5.948-.948l.395-1.183A.75.75 0 0 1 16.5 15Z"
                                        clip-rule="evenodd"></path>
                                </svg></div>
                                <div class="rounded-lg border shadow-sm flex flex-col !max-h-max bg-zinc-950 p-5 !px-[22px] !py-[22px] text-base font-normal leading-6 text-white backdrop-blur-xl dark:border-zinc-800 dark:!bg-white/5 dark:text-white md:text-base md:leading-[26px]"
                                        >
                                            <!-- Div para a mensagem atual -->
                                            <div class="text-base font-normal mb-4">
                                            <p><strong>Sua Mensagem</strong></p>
                                            <p>&nbsp;</p>
                                            <p>{{ advice }}</p>
                                            </div>

                                            <hr class = "border-t border-zinc-700 dark:border-zinc-500 my-4" />

                                            <!-- Div para a caixa de mensagens -->
                                            <div class="text-base font-normal">
                                            <p><strong>Sua caixa de Mensagem</strong></p>
                                            <p>&nbsp;</p>
                                            <ul class="list-disc pl-5">
                                                <!-- Mostra as últimas mensagens -->
                                                 <li v-for="(message, index) in messages"  :key="index">
                                                    {{ message }}
                                                 </li>
                                            </ul>
                                            </div>
                                        </div>
                        </div>
                    </div> 
                </div>
            </div>

        </div>
      
    </div>

</template>


<script>
export default {
  data() {
    return {
        
      advice: "", // Armazena a resposta da API
      messages: [] //Armazena as mensagens
      };
  },
  methods: {

    cliquei() {
      console.log("ta vivo");
    },
    async Buscar() {
      try {
        const response = await fetch("https://api.adviceslip.com/advice");
        const data = await response.json();
        this.advice = data.slip.advice; // Exibe o conselho recebido
        this.messages.push(data.slip.advice);

        if (this.messages.length > 3) {
            this.messages.shift();
        }

      } catch (error) {
        console.error("Erro ao buscar a API:", error);
      }
    },


  },
};
</script>
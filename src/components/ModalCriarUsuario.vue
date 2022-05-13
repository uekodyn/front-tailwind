<template>
   <div>
      <p class="text-blue-500  font-bold  text-sm px-6 py-3 mr-1 mb-1 " v-on:click="toggleModal()">
         Crie sua conta
      </p>
      <div v-if="showModal"
         class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex">
         <div class="relative w-auto my-6 mx-auto max-w-3xl">
            <!--content-->
            <div
               class="border-0 rounded-lg shadow-lg relative flex flex-col w-full bg-white outline-none focus:outline-none">
               <!--header-->
               <div class="flex items-start justify-between p-5 border-b border-solid border-slate-200 rounded-t">
                  <h3 class="text-3xl font-semibold">
                     Criação de Usuário
                  </h3>
                  <button
                     class="p-1 ml-auto bg-transparent border-0 text-black opacity-5 float-right text-3xl leading-none font-semibold outline-none focus:outline-none"
                     v-on:click="toggleModal()">
                     <span
                        class="bg-transparent text-black opacity-5 h-6 w-6 text-2xl block outline-none focus:outline-none">
                        ×
                     </span>
                  </button>
               </div>
               <!--body form -->
               <div class="relative p-6 flex-auto space-y-3">
                  <div class="relative  w-36 h-36 justify-center overflow-hidden bg-gray-100 rounded-full dark:bg-gray-600">
                     <svg class="absolute  w-36 h-36 text-gray-400 " fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd"></path></svg>
                  </div>
                  <input 
                     type="text" 
                     class="px-3 rounded-lg py-2 placeholder-gray-200 border border-gray-300 w-full"
                     placeholder="Seu Nome">
                  <input 
                     type="text" 
                     class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
                     placeholder="Seu Telefone">
                  <input 
                     type="text" 
                     class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
                     placeholder="Seu Email">
                  <input 
                     type="text" 
                     class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
                     placeholder="Seu Telefone">


               </div>
               <!--footer-->
               <div class="flex items-center justify-end p-6 border-t border-solid border-slate-200 rounded-b">
                  <button
                     class="text-blue-500 bg-transparent border border-solid border-blue-500 hover:bg-blue-500 hover:text-white active:bg-red-600 font-bold uppercase text-sm px-6 py-3 rounded outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150"
                     type="button" v-on:click="toggleModal()">
                     Cancelar
                  </button>
                  <button
                     class="text-blue-500 background-transparent font-bold uppercase px-6 py-2 text-sm outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150"
                     type="button" v-on:click="toggleModal()">
                     Criar
                  </button>
               </div>
            </div>
         </div>
      </div>
      <div v-if="showModal" class="opacity-25 fixed inset-0 z-40 bg-black"></div>
   </div>
</template>

<script>
export default {
   name: "regular-modal",
   data() {
      return {
         showModal: false
      }
   },
   methods: {
      toggleModal: function () {
         this.showModal = !this.showModal;
      }
   }
}
</script>
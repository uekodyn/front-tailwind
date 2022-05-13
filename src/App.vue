<template>
   <!-- img full -->
   <div class="min-h-screen bg-white flex ">
      <div class="hidden lg:block relative w-0 flex-1 bg-gray-900">
         <div class="flex h-full justify-center items-center">
            <img src="./assets/perfillogo.svg" alt="" class="h-80 w-full">
         </div>
      </div>

      <!-- img small and form -->
      <div class="flex flex-1 flex-col justify-center px-4 py-12 sm:px-6 lg:flex-none lg:px-20 xl:px-24">
         <div class="mx-auto w-full max-w-sm lg:w-96 ">
            <div>
               <img src="./assets/perfillogo.svg" alt="" class="lg:hidden h-24 w-full">
               <H2 class="mt-6 text-3xl font-semibold text-blue-400">Entrar</H2>
               <div class="flex justify-start mt-2">
                  <p class=" text-sm text-gray-600 max-w mt-1 ">Novo por aqui? 
                     </p>
                     <ModalCriarUsuario  class="max-w ml-2"/>
               </div>
            </div>
            <!-- form -->
            <div class="mt-6">
               <form action="">
                  <div class="mb-4">
                     <input type="text" placeholder="E-mail"
                        class="apperance-none shadow-md block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none">
                  </div>
                  <div class="mb-4">
                     <input type="password" 
                        maxlength="12"
                        placeholder="Senha"
                        class="apperance-none shadow-md block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none">
                  </div>
                  <div class="flex justify-between mx-1">
                     <label class="block text-gray-500 font-bold my-4">
                        <input 
                           type="checkbox"
                           class="leading-loose text-blue-600">
                           <span class="py-2 text-sm text-gray-600 leading-snug"> Lembrar login </span></label> <label class="block text-gray-500 font-bold my-4"><a
                              href="#"
                              class="cursor-pointer tracking-tighter text-gray-500 border-b-2 border-gray-200 hover:border-gray-400"><span>Esqueceu a senha?</span></a></label>
                  </div>
                  <p class="text-sm text-center font-semibold">ou login com</p>
                  <div class="btn-wrapper text-center my-4">
                  <button class="bg-white active:bg-blueGray-50 text-blueGray-700 font-normal px-4 py-2 rounded outline-none focus:outline-none mr-2 mb-1 uppercase shadow hover:shadow-md inline-flex items-center font-bold text-xs ease-linear transition-all duration-150" type="button">
                     <img alt="..." class="w-5 mr-1" src="https://demos.creative-tim.com/notus-js/assets/img/github.svg">Github </button>
                  <button class="bg-white active:bg-blueGray-50 text-blueGray-700 font-normal px-4 py-2 rounded outline-none focus:outline-none mr-1 mb-1 uppercase shadow hover:shadow-md inline-flex items-center font-bold text-xs ease-linear transition-all duration-150" type="button">
                     <img alt="..." class="w-5 mr-1" src="https://demos.creative-tim.com/notus-js/assets/img/google.svg">Google</button>
                  </div>
                  <div class="mb-4">
                     <button class="inline-block w-full py-4 px-8 leading-none text-white bg-blue-400 hover:bg-blue-500 font-semibold rounded shadow">Entrar</button>
                  </div>
               </form>
            </div>
         </div>
      </div>
   </div>
</template>

<script>
import ModalCriarUsuario from "./components/ModalCriarUsuario.vue"


export default {
   name: "App",
   components: { ModalCriarUsuario }
}
</script>


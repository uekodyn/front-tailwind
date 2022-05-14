<template>
   <div>
      <p class="text-blue-500 cursor-pointer font-bold text-sm py-1 mr-1 mx-2" v-on:click="toggleModal()">
         Crie sua conta
      </p>
      <div v-if="showModal"
         class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex">
         <div class="relative w-auto my-6 mx-auto max-w-3xl">
            <!--content-->
            <div
               class="border-0 rounded-lg shadow-lg relative flex flex-col w-full bg-white outline-none focus:outline-none">
               <!--header-->
               <div class="flex  justify-center p-3 px-8 mx-8 border-b border-solid border-slate-200 rounded-t">
                  <h3 class="text-xl font-bold">
                     Cadastro de usuário
                  </h3>
               </div>
               <!--body form -->
               <div class="relative p-6 -mt-2 flex-auto ">
                  <!-- <div class="flex justify-start">
                     <span class="text-sm font-semibold">Avatar</span>
                  </div> -->


                  <div class="relative justify-center  flex">
                        <!-- Card Avatar -->
                        <section class="w-64 mx-auto bg-[#20354b] rounded-2xl px-6 py-4 shadow-md">
                           <div class="flex items-center justify-between">
                                 <span class="text-gray-400 text-sm">Perfil</span>
                                 <span class="text-emerald-400">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" />
                                 </svg>
                                 </span>
                           </div>
                           <div class="flex justify-between">
                              <div  class="mt-2 w-fit mx-auto">
                                    <label>
                                    <div v-if="imageData.length < 1" class="file-upload-form relative cursor-pointer w-20 h-20 justify-center overflow-hidden bg-gray-100 rounded-full dark:bg-gray-600">
                                       <svg class="absolute  w-20 h-20 text-gray-400 " fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd"></path></svg>
                                    </div>
                                    <input type='file' class="hidden" @change="previewImage" accept="image/*"  />        
                                    <!-- avatar preview -->
                                    <div class="image-preview" v-if="imageData.length > 0">
                                       <img class="preview relative cursor-pointer w-20 h-20 justify-center overflow-hidden bg-gray-100 rounded-full dark:bg-gray-600" :src="imageData">
                                    </div>
                                    </label>
                              </div>

                           <div class="mt-2 ">
                              <h2 class="text-white font-bold text-xl tracking-wide"></h2>
                           </div>  
                           </div>
                        </section>                  
                  </div>
                  <!-- form valid -->
                  <form id="Form" action="" v-on:submit.prevent="checkForm">
                     <h4 class="text-sm font-semibold">Nome</h4>
                     <input 
                        type="text" 
                        v-model="name"
                        class="px-3 mb-3 apperance-none shadow-md block w-full py-3 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none"
                        placeholder="Seu Nome">
                     <h4 class="text-sm font-semibold">E-mail</h4>
                     <input 
                        type="email" 
                        v-model="email"
                        class="mb-3 apperance-none shadow-md block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none"
                        placeholder="Seu E-mail">
                     <div class="flex justify-between">
                        <div class="mr-2">
                        <h4 class="text-sm font-semibold">Telefone</h4>
                        <input 
                           type="tel" maxlength="12"
                           onkeypress="return event.charCode >= 48 && event.charCode <= 57"
                           class="mb-3 apperance-none shadow-md block w-full mr-4  py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none"
                           placeholder="Seu Telefone">
                        </div>
                        <div class="ml-2">
                           <h4 class="text-sm font-semibold  ">Idade</h4>
                        <input 
                           type="number" 
                           class="mb-3 apperance-none shadow-md block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none"
                           placeholder="Sua Idade">
                        </div>
                     </div>
                  <!-- term privacy -->
                  <div>
                     <label class="inline-flex items-center cursor-pointer">
                        <input id="customCheckLogin" type="checkbox" class="form-checkbox border-0 rounded text-blueGray-700 ml-1 w-5 h-5 ease-linear transition-all duration-150">
                        <span class="ml-2 text-xs font-semibold text-blueGray-600">
                        Estou de acordo com o
                        <a href="javascript:void(0)" class="text-blue-500">
                           Termos de uso
                        </a> e a 
                        <a href="javascript:void(0)" class="text-blue-500">
                           Política de Privacidade.
                        </a>
                        </span>
                     </label>
                  </div>
                  <!-- error valid -->
                  <ul><li class="text-red-400" v-for="error in errors">{{error}}</li>
                     </ul>
                  <!-- sign up with -->
                  <p class="text-sm text-center font-semibold">entrar com</p>
                  <div class="btn-wrapper text-center my-4">
                  <button class="bg-white active:bg-blueGray-50 text-blueGray-700 font-normal px-4 py-2 rounded outline-none focus:outline-none mr-2 mb-1 uppercase shadow hover:shadow-md inline-flex items-center font-bold text-xs ease-linear transition-all duration-150" type="button">
                     <img alt="..." class="w-5 mr-1" src="https://demos.creative-tim.com/notus-js/assets/img/github.svg">Github </button>
                  <button class="bg-white active:bg-blueGray-50 text-blueGray-700 font-normal px-4 py-2 rounded outline-none focus:outline-none mr-1 mb-1 uppercase shadow hover:shadow-md inline-flex items-center font-bold text-xs ease-linear transition-all duration-150" type="button">
                     <img alt="..." class="w-5 mr-1" src="https://demos.creative-tim.com/notus-js/assets/img/google.svg">Google</button>
                  </div>
               
                  <!--footer-->
                  <div class="flex items-center justify-between p-3 -mb-6 border-t border-solid border-slate-200 rounded-b">
                     <button
                        class="text-blue-500 background-transparent font-semibold  px-6 py-2 text-sm outline-none focus:outline-none mr-1  ease-linear transition-all duration-150"
                        type="button" v-on:click="toggleModal()">
                        Cancelar
                     </button>
                     <button
                        class="text-blue-500 bg-transparent border border-solid border-blue-500 hover:bg-blue-500 hover:text-white active:bg-red-600 font-bold text-sm px-6 py-3 rounded outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150"
                        type="submit" v-on:click="formValid()" >
                        Criar
                     </button>
                  </div>
                  </form>
               </div>
            </div>
         </div>
      </div>
      <div v-if="showModal" class="opacity-25 fixed inset-0 z-40 bg-black"></div>
   </div>
</template>

<script>
export default {
   name: "cadastro-modal",
   data() {
      return {
         showModal: false,
         name: null,
         email: null,
         errors: [],
         title: '',
         imageData: ""
      }
   },
   methods: {
      toggleModal: function () {
         this.showModal = !this.showModal;
      },
      checkForm: function(){
         this.errors = [];

         if(!this.name){
            this.errors.push('O nome deve ser preenchido!');
         }
         if(!this.email){
             this.errors.push('O email deve ser preenchido!');
         }
         if(this.name && this.email){
            this.errors = [];
         };
      },
      formValid: function(){
         if(this.name && this.email) {
            document.getElementById("Form").reset();
            this.showModal = false;
            this.errors = [];
            this.$emit('Criou')
         };
      },
      previewImage: function(event) {
            // Referenciando Dom input element
            var input = event.target;
            // verifica se tem arquivo antes de ler
            if (input.files && input.files[0]) {
                // cria um novo FileReader para ler a image e converter a base64 formato
                var reader = new FileReader();
                // Define a function de callback a ser executada, quando o FileReader terminar seu trabalho
                reader.onload = (e) => {
                    // arrow funcion usada aqui, para que "this.imageData" se refira ao componente imageData do Vue
                    // Lê a imagem como base64 e define como imageData
                    this.imageData = e.target.result;
                }
                // Inicia o trabalho do reader - lendo o arquivo como um URL de dados 
                reader.readAsDataURL(input.files[0]);
            }
      }
   }
}
</script>

<style>
img.preview {
    background-color: white;
    border: 1px solid #DDD;
    padding: 5px; 
}

</style>
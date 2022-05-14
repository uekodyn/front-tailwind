<template>
   <div class="relative justify-center flex">
      <!-- Card Avatar -->
      <section class="w-96 mx-auto  rounded-2xl bg-[#071e34] px-6 py-4 my-2 shadow-xl max-w-xs hover:scale-110 transition duration-300 ease-in-out " >
         <div class="flex items-center justify-between">
               <span class="text-gray-400 text-sm">Perfil</span>
               <span class="text-emerald-400">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z" />
               </svg>
               </span>
         </div>
         <div class="flex  justify-start">
            <div  class="mt-2 w-fit">
               <label>
               <div v-if="imageData.length < 1" class="max-w-xs hover:scale-110 transition duration-300 ease-in-out file-upload-form relative cursor-pointer w-20 h-20 justify-center overflow-hidden bg-gray-100 rounded-full dark:bg-gray-600">
                  <svg class="absolute  w-20 h-20 text-gray-400 " fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd"></path></svg>
               </div>
               <input type='file' class="hidden" @change="previewImage" accept="image/*"  />        
               <!-- avatar preview -->
               <div class="max-w-xs hover:scale-110 transition duration-300 ease-in-out image-preview relative cursor-pointer w-20 h-20 justify-center overflow-hidden bg-gray-100 rounded-full dark:bg-gray-600" v-if="imageData.length > 0">
                  <img class="preview rounded-full" :src="imageData">
               </div>
               </label>
            </div>
            <div class="mt-2 mx-2 max-w-xs hover:scale-110 transition duration-300 ease-in-out">
               <h2 class="text-gray-400 font-semibold text-lg mx-2 tracking-wide">{{ name }}</h2>
               <h4 class="text-gray-400 font-semibold text-xs mx-2 tracking-wide">{{ email }}</h4>

            </div>  
         </div>
      </section>                  
   </div>
</template>
<script>

export default {
   name: "card-perfil",
   data() {
      return {
         imageData: '',
         localName: '',
         localEmail: '',
      }
   },
   props: {
      name: { type: String, default: '',},
      email: { type: String, default: '',}
   },
   created() {
      this.localName = this.name;
      this.localEmail = this.email;
   },
   methods: {
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
    /* padding: 5px;  */
}
</style>
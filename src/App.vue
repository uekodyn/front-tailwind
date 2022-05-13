<template>
  <div class="w-screen h-screen flex items-center justify-center bg-blue-400">
    <!-- <div class="bg-white rounded-3xl shadow-xl w-full sm:10/12 md:w-8/12 lg:w-6/12 p-6"> -->
      <div class="bg-white mx-auto max-w-md py-8 px-12 shadow rounded-xl">
      <!-- <h4 class="font-semibold text-md mb-3 border-b border-gray-200">Identificação de usuário</h4> -->
      <!-- <div class="mb-4 justify-center">
        <img class="" width="200" height="300px" src="./assets/autlogo.svg" alt="">
      </div> -->
      <div class="space-y-3">
        <input
          type="text"
          class="px-3 rounded-lg py-2 placeholder-gray-200 border border-gray-300 w-full"
          placeholder="Seu Nome"
        >
        <input
          type="text"
          class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
          placeholder="Seu Telefone"
        >
        <input
          type="text"
          class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
          placeholder="Seu Email"
        >
        <input
          type="text"
          class="px-3 py-2 rounded-lg placeholder-gray-200 border border-gray-300 w-full"
          placeholder="Seu Telefone"
        >

        <div class="text-right">
          <button class="rounded text-sm px-3 py-2 bg-blue-400 hover:bg-blue-500 text-gray-900">
            LOGIN
          </button>
        </div>
      </div>
    </div>
  </div>


</template>

<script>
export default {
  name: 'App',
}
</script>


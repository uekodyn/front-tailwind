<template>
  <!-- img full -->
  <div class="min-h-screen bg-white flex">
    <div class="hidden lg:block relative w-0 flex-1 bg-gray-900">
      <div class="flex h-full justify-center items-center">
        <img src="./assets/perfillogo.svg" alt="" class="h-80 w-full">
      </div>
    </div>

<!-- img small and form -->
    <div class="flex flex-1 flex-col justify-center px-4 py-12 sm:px-6 lg:flex-none lg:px-20 xl:px-24">
      <div class="mx-auto w-full max-w-sm lg:w-96 ">
        <div>
          <img src="./assets/perfillogo.svg" alt="" class="lg:hidden h-20 w-full">
          <H2 class="mt-6 text-3xl font-semibold text-blue-400">Entrar</H2>
          <p class="mt-2 text-sm text-gray-600 max-w">Novo por aqui? <a href="#" class="font-medium text-blue-400" ></a></p>
        </div>
        <div class="mt-6">
          <form action="">
            <div class="mb-4">
              <input 
                type="text" 
                placeholder="E-mail"
                class="apperance-none block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none">
            </div>
            <div class="mb-4">
              <input 
                type="text" 
                placeholder="Senha"
                class="apperance-none block w-full py-3 px-4 leading-tight text-gray-700 bg-gray-50 focus:bg-white border border-gray-200 focus:border-gray-500 rounded focus:outline-none">
            </div>
            <div class="mb-4">
              <button class="inline-block w-full py-4 px-8 leading-none text-white bg-blue-400 hover:bg-blue-900 font-semibold rounded shadow">Entrar</button>
            </div>

          </form>
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


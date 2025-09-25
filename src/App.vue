<script setup></script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 text-bg-secondary runded-3 ">
      <h1 class="d-flex justify-content-center align-items-center">Calculadora</h1>
      <p class="d-flex justify-content-center align-items-center">
        Descubra o resultado de sua conta aritmética!
      </p>
  </header>
  <form class="mt-5 d-flex justify-content-center align-items-center"> 
    <div class="row">
      <div class="col-4">
        <input type="number" placeholder="0" class="border border-3 me-5"/>
      </div>
      <div class="col-2">
        <select name="" id="" class="p-1 w-100 me-2">
          <option value="vazio"></option>
          <option value="adicao">+</option>
          <option value="subtracao">-</option>
          <option value="multiplicacao">x</option>
          <option value="divisao">/</option>
        </select>
      </div>
      <div class="col-4">
        <input type="number" placeholder="0" class="border border-3"/>
      </div>
      <div class="col-2">
        <button type= "submit" class="btn btn-outline-primary btn-sm"> Calcular</button>
      </div>
    </div>
  </form>
  <section>
    <div class="d-flex justify-content-center align-items-center mt-5">
      <h2>Resultado: </h2>
      <h3 class="ms-3">0</h3>
    </div>
  </section>
  
  
  </div>
</template>

<style scoped></style>

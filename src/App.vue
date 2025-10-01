<script setup>
import {reactive, watch} from 'vue';

const estado = reactive({
  resultado:0,
  expressoes:'',
  numero1: 0,
  numero2: 0,
});

const mais = (a, b) => {
  return a + b;
};

const menos = (a, b) =>{
  return a - b;
};

const multiplica = (a, b) => {
  return a * b;
};

const divide = (a, b) => {
  return a / b;
};

const calcular = () =>{

  switch(estado.expressoes){
    case 'adicao':
      estado.resultado = mais(estado.numero1, estado.numero2);
      break;
    case 'subtracao':
      estado.resultado = menos(estado.numero1, estado.numero2);
      break;
    case 'multiplicacao':
      estado.resultado = multiplica(estado.numero1, estado.numero2);
      break;
    case 'divisao':
      estado.resultado = divide(estado.numero1, estado.numero2);
      break;
    default:
      estado.resultado = 0;
  }
}

watch(
  () => [estado.numero1, estado.numero2, estado.expressoes],
  calcular
);
</script>

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
          <input type="number" placeholder="0"  v-model.number="estado.numero1" class=" form-control border border-3 me-5"/>
        </div>
        <div class="col-2">
          <select v-model="estado.expressoes" @change="calcular" class="form-control p-1 w-100 me-2">
            <option value="vazio"></option>
            <option value="adicao">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
          </select>
        </div>
        <div class="col-4">
          <input type="number" placeholder="0" v-model.number="estado.numero2" class="form-control border border-3"/>
        </div>
      </div>
    </form>
    <section>
      <div class="d-flex justify-content-center align-items-center mt-5">
        <h2>Resultado:</h2>
        <h3 class="ms-3">
          {{ estado.resultado }}
        </h3>
      </div>
    </section>
  </div>
</template>

<style scoped></style>

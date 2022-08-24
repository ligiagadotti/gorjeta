<script setup>
import { ref } from "vue";
const pessoas = ref("");
const preco = ref("");
</script>
<template>
  <main>
    <h1>Calculadora de Gorjetas</h1>

    <label>Valor da Conta?</label>
    <input type="number" v-model="preco" />
    <label>Como foi o Serviço?</label>
    <select name="Qualidade do serviço" v-model="gorjeta" id="asd">
      <option value="5">5% (Péssimo)</option>
      <option value="10">10% (Ruim)</option>
      <option value="15">15% (Ok)</option>
      <option value="20">20% (Bom)</option>
      <option value="25">25% (Mais que Bom)</option>
      <option value="30">30% (Perfeito)</option>
    </select>
    <label>Quantas pessoas irão dividir?</label>
    <input type="number" v-model="pessoas" />
    <h4>
      Valor da conta: R${{ (preco * (1 + gorjeta / 100)) / pessoas }} para cada
      pessoa
    </h4>
  </main>
</template>

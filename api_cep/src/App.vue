<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      endereco: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const { data } = await axios.get(url);
      this.endereco = data;
    },
  },
};
</script>

<template>
  <h2>Buscar CEP</h2>
  <form @submit.prevent="buscar">
    <input type="text" v-model="cep" placeholder="Digite o CEP" />
    <button type="submit">Buscar</button>
  </form>
  <form>
    <label for="rua">Rua</label>
    <input name="rua" type="text" v-model="endereco.logradouro" />
    <label for="numero">Numero</label>
    <input name="numero" type="text" v-model="endereco.numero" />
    <label for="complemeto">complemeto</label>
    <input name="complemento" type="text" v-model="endereco.complemento" />
    <label for="cidade">Cidade</label>
    <input name="cidade" type="text" v-model="endereco.localidade" />
    <label for="estado">Estado</label>
    <input name="estado" type="text" v-model="endereco.uf" />
  </form>
</template>

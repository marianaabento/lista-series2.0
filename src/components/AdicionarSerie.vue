<template>
  <div class="input-group">
      <!-- <input @keyup.enter="adicionarSerie" v-model="novaSerie" type="text" -->
      <!-- <entrada-dados :value="novaSerie" @input="associarValor" /> -->
      <entrada-dados @salvar="adicionarSerie" v-model="novaSerie" /> 
      <span class="input-group-btn">
        <button @click="adicionarSerie" class="btn btn-primary">
          Adicionar 
        </button>
      </span>
    </div>
</template>

<script>
import EntradaDados from '@/components/templates/EntradaDados'
export default {
    components: { EntradaDados },
    data() {
        return{
            novaSerie: "",
        };
    },
    methods: {
        adicionarSerie() {
          this.$emit("adicionarSerie", this.novaSerie);
          this.novaSerie = ""; 
        },
    },
};
</script>

<style>

</style>
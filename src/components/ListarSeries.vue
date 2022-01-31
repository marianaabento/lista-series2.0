<template>
  <ul>
      <li 
        v-for="(serie, index) in series" 
        :key="index" 
        :class="{ removed: serie.checked }"
      >
        <input type="checkbox" v-model="serie.checked" />
        <label> {{ serie.titulo }}</label>
      </li>
    </ul>
</template>

<script>
export default {
  props: {
    series: {
      type: Array,
      default() {
        return [{ titulo: "Atividade padrão", checked: false }]
      },
    },
  },
};
</script>

<style>

</style>
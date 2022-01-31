<template>
<section>
  <cabecalho :valor="titulo"/>
  <div class="container">
    <adicionar-serie v-on:adicionarSerie="adicionarSerie" />
    <listar-series :series="series"/>
    <footer>
      <em>Altere aqui o título da sua lista de séries</em>
      <entrada-dados v-model="titulo" type="text" />
    </footer>
  </div>
  <rodape />
</section>
</template>

<script>
import Cabecalho from '@/components/Cabecalho';
import Rodape from '@/components/Rodape';
import ListarSeries from '@/components/ListarSeries';
import AdicionarSerie from '@/components/AdicionarSerie';
import EntradaDados from '@/components/templates/EntradaDados';
export default {
name: "App",
components: { Cabecalho, Rodape, ListarSeries, AdicionarSerie, EntradaDados },
  data() {
    return {
      titulo: "Minha lista de séries",
      series: [
        { titulo: "House of Cards", checked: false},
        { titulo: "How I met Yor Mother", checked: false},
        { titulo: "Modern Family", checked: true},
        { titulo: "Dinasty", checked: false},
        { titulo: "Seinfield", checked: false},
      ],
    };
  },
  methods: {
    adicionarSerie(novaSerie) {
      this.series.push({
        titulo: novaSerie,
        checked: false,
      });
    },
  },
}
</script>

<style>
.container {
  width: 60%;
  margin: 20px auto 0px auto;
}

ul li {
  list-style: none;
}

.removed {
  color: gray;
}

.removed label {
  text-decoration: line-through;
}

</style>

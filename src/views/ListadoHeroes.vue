<template>
  <div class="home">
    <BuscadorHeroe @paso="clicBuscHeroe"></BuscadorHeroe>
    <Heroe></Heroe>
  </div>
</template>

<script>
// @ is an alias to /src
import BuscadorHeroe from "@/components/BuscadorHeroe.vue";
import Heroe from "@/components/Heroe.vue";

export default {
  methods: {
    clicBuscHeroe(buscar) {
      var Buscar = buscar;
      console.log(Buscar);
    },
  },
  computed: {},
  name: "ListadoHeroes",
  components: {
    BuscadorHeroe,
    Heroe,
  },
};
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1>App heroes</h1>
        <BuscadorHeroe @paso="clicBuscHeroe"></BuscadorHeroe>
      </div>
      <div class="col-10">
        <button
          @click="mostrar = !mostrar"
          type="submit"
          class="btn btn-primary ext"
        >
          Agregar heroe
        </button>
        <Heroe></Heroe>
      </div>
      <div v-show="mostrar" class="col-2">
        <Form></Form>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import BuscadorHeroe from "@/components/BuscadorHeroe.vue";
import Heroe from "@/components/Heroe.vue";
import Form from "@/components/Form.vue";

export default {
  data() {
    return {
      mostrar: false,
    };
  },
  components: {
    BuscadorHeroe,
    Heroe,
    Form,
  },
  methods: {
    clicBuscHeroe(buscar) {
      var Buscar = buscar;
      console.log(Buscar);
    },
  },
  computed: {},
  name: "ListadoHeroes",
};
</script>

<style>
.ext {
  margin: 20px;
}
</style>

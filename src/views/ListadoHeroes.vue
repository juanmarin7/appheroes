<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <h1>App heroes</h1>
        <BuscadorHeroe @pasoBuscar="BuscHeroe"></BuscadorHeroe>
      </div>
      <div class="col-6">
        <button
          @click="mostrar = !mostrar"
          type="submit"
          class="btn btn-primary ext"
        >
          Agregar heroe
        </button>
      </div>
      <div class="col-2" v-show="mostrar">
        <div>
          <form>
            <div class="mb-2">
              <h2>Heroe</h2>
              <input
                placeholder="id"
                v-model="id"
                type="text"
                class="form-control"
              />
            </div>
            <div class="mb-2">
              <input
                placeholder="Nombre"
                v-model="name"
                type="text"
                class="form-control"
              />
            </div>
            <div class="mb-2">
              <input
                placeholder="Poder"
                v-model="poder"
                type="text"
                class="form-control"
              />
            </div>
            <div class="mb-2">
              <input
                placeholder="URL Imagen"
                v-model="URLimg"
                type="text"
                class="form-control"
              />
            </div>

            <button @click="guardarH()" type="submit" class="btn btn-primary">
              Guardar
            </button>
          </form>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <div class="col-3 tst">
            <Heroe
              v-for="(h, $index) in filterH"
              :key="$index"
              :heroe="h"
              :posicion="$index"
              @eliminar="EliminarH()"
              >{{ h.poder }}</Heroe
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import BuscadorHeroe from "@/components/BuscadorHeroe.vue";
import Heroe from "@/components/Heroe.vue";

export default {
  components: {
    BuscadorHeroe,
    Heroe,
  },
  name: "ListadoHeroes",
  props: {},
  data() {
    return {
      mostrar: false,
      inputData: null,
      buscar: null,
      id: null,
      name: null,
      poder: null,
      URLimg: null,

      ListHeroes: [
        {
          id: 1,
          name: "Batman",
          poder: "Mañas",
          URLimg:
            "https://i.pinimg.com/originals/2f/ea/a3/2feaa346bd96e29c20ccacf92acd7f16.png",
        },
        {
          id: 2,
          name: "Superman",
          poder: "Mañas",
          URLimg:
            "https://i.pinimg.com/originals/93/36/ca/9336cac3bdf0d118df90bc1ac2bf06a8.png",
        },
        {
          id: 3,
          name: "Spiderman",
          poder: "Telaraña",
          URLimg:
            "https://i.pinimg.com/originals/97/de/e5/97dee5433d3cf33befeb676e13fc727f.png",
        },
      ],
    };
  },
  computed: {
    filterH() {
      if (this.inputData) {
        return this.ListHeroes.filter((heroe) => {
          return heroe.name.toLowerCase().includes(this.inputData.toLowerCase());
        });
      } else {
        console.log("no entro");
        return this.ListHeroes;
      }
    },
  },
  methods: {
    BuscHeroe(inputData) {
      console.log(inputData);
    },
    guardarH() {
      console.log(this.id);
      if (this.id != null) {
        const newHeroe = {
          id: this.id,
          name: this.name,
          poder: this.poder,
          URLimg: this.URLimg,
        };
        this.ListHeroes.push(newHeroe);
      } else {
        alert("Debe ingresar todos los valores");
      }
      (this.id = null),
        (this.name = null),
        (this.poder = null),
        (this.URLimg = null);
    },
    EliminarH(posicion) {
      let elim = this.ListHeroes.indexOf(posicion);
      this.ListHeroes.splice(elim, 1);
    },
  },
};
</script>

<style>
.ext {
  margin: 20px;
}
.tst {
  display: contents;
}
</style>

<template>
  <div class="container">
    <div class="row">
      <div  class="col-4" v-for="ListHeroe of ListHeroes" v-bind:key="ListHeroe">
        <div class="card">
          <h5 class="card-title">
            {{ ListHeroe.name }}
          </h5>

          <img width="200" height="200" v-bind:src="ListHeroe.imgURL" />
          <div class="card-body">
            <a href="#" class="btn btn-primary">Eliminar heroe</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  
  data: function () {
    return {
      ListHeroes: [
        {
          id: "1",
          name: "Batman",
          poder: "Mañas",
          imgURL:
            "https://i.pinimg.com/originals/2f/ea/a3/2feaa346bd96e29c20ccacf92acd7f16.png",
        },
        {
          id: "2",
          name: "Superman",
          poder: "Mañas",
          imgURL:
            "https://i.pinimg.com/originals/93/36/ca/9336cac3bdf0d118df90bc1ac2bf06a8.png",
        },
        {
          id: "3",
          name: "Spiderman",
          poder: "Telaraña",
          imgURL:
            "https://i.pinimg.com/originals/97/de/e5/97dee5433d3cf33befeb676e13fc727f.png",
        },
      ],
    };
  },
  methods: {
    ListaHeroes() {
      this.$emit("lista", this.ListHeroes);
    },
  },
  computed:{
     filtroLista() {
      if(this.buscar.trim().lengt>0){
         return this.ListHeroes.filter((Poder)=>Poder.poder.toLowerCase().includes(this.buscar.trim()))
      }
       
    },
  },
  name: "Heroe",
};
</script>
<style></style>

<template>
  <div class="card">
    <h5 class="card-title">
      {{ heroe.name }}
    </h5>

    <img :src="heroe.URLimg" width="200" height="200" />
    <div class="card-body">
      <a @click="eliminarH()" href="#" class="btn btn-primary"
        >Eliminar heroe</a
      >
    </div>
  </div>
</template>
<script>
export default {
  name: "Heroe",
  props: {
    heroe: {
      type: Object,
      default: () => {},
    },
    posicion: {
      type: Number,
      default: -1,
    },
  },
  methods: {
    eliminarH() {
      this.$emit("eliminar", this.posicion);
    },
  },
};
</script>
<style>
.tst {
  display: inline;
}
</style>

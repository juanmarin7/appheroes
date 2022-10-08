<template>
  <div class="container">
    <div class="row">
      <div class="col-4"></div>
      <div class="col-4">
        <div class="input-group mb-3">
          <input
            v-model="buscar"
            type="text"
            class="form-control"
            placeholder="Buscar heroe"
          />
          <button
            class="btn btn-outline-secondary"
            type="button"
            id="button-addon2"
            @click="recBuscar"
          >
            Buscar
          </button>
        </div>
        <div class="col-4"></div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    buscar: "",
  }),
  name: "BuscadorHeroe",
  props: {},
  methods: {
    recBuscar() {
      this.$emit("pasoa", this.buscar);
    },
  },
};
</script>
<style></style>

<template>
  <div>
    <div class="row">
      <div class="input-group mb-3">
        <input
          v-model="inputData"
          type="text"
          class="form-control"
          placeholder="Buscar heroe"
        />
        <button
          class="btn btn-outline-secondary"
          type="button"
          id="button-addon2"
          @click="buscarH()"
        >
          Buscar
        </button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    buscar: null,
  }),
  name: "BuscadorHeroe",
  methods: {
    buscarH() {
      this.$emit("pasoBuscar", this.inputData);
    },
  },
};
</script>
<style></style>

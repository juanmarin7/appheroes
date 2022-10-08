<template>
  <div>
    <div class="row">
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
      this.$emit("paso", this.buscar);
    },
  },
};
</script>
<style></style>

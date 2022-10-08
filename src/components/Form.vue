<template>
  <div>
    <form>
      <div class="mb-3">
        <h1>Heroe</h1>
        <label for="#" class="form-label">Id</label>
        <input  type="text" class="form-control" />
      </div>
      <div class="mb-3">
        <label for="" class="form-label">Nombre</label>
        <input type="text" class="form-control" id="" />
      </div>
      <div class="mb-3">
        <label for="" class="form-label">Poderes</label>
        <input type="text" class="form-control" id="" />
      </div>
      <div class="mb-3">
        <label for="" class="form-label">URL de foto</label>
        <input type="text" class="form-control" id="" />
      </div>

      <button type="submit" class="btn btn-primary">Guardar</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",
};
</script>

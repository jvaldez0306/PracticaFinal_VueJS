<template>
  <h1>Inventario de Activos</h1>
  <div class="row">
    <div class="col m12 card-panel">
      <div class="col m4">
        <label>Tipo de Activo</label>
        <input type="text" v-model="tipo">
      </div>
      <div class="col m4">
        <label>marca</label>
        <input type="text" v-model="marca">
      </div>
    </div>
  </div>

<div class="row">
  <div class="col m3">
    <label>Modelo</label>
    <input type="text" v-model="modelo">
  </div>
  <div class="col m4">
    <label>Estado</label>
    <select v-model="estado_activo">
      <option value="N">Nuevo</option>
      <option value="U">Usado</option>
      <option value="D">Desuso</option>

    </select>
  </div>
</div>
 
</template>

<script>
import M from 'materialize-css'

export default {
  name: 'App',
  mounted()
  {
    this.axios.get('https://prueba.com')
    .then(() =>{

    });
  },
  methods:{
    saludar()
    {
      M.toast({html: 'Hola Mundo'});
    }
  }

  }

</script>
<style>
#app{
  font-family: Avenir, Helvetica, sans-serif;
  -webtik-font-smoothing: antialiased;
  
}
</style>

<template>
  <div class="container">
    <h1>Inventario de Activos</h1>
      <h3>Registro de Activos</h3>
        <div class="row">
          <div class="col m12 card-panel">
             <form @submit.prevent="agregarActivo">
                <div class="row">
                  <div class="col m4">
                    <label>Tipo de Activo</label>
                    <input type="text" v-model="tipo">
                  </div>
                  <div class="col m4">
                    <label>Marca</label>
                    <input type="text" v-model="marca">
                  </div>
                </div>            
                <div class="row">
                  <div class="col m4">
                    <label>Modelo</label>
                    <input type="text" v-model="modelo">
                  </div>
                  <div class="col m4">
                    <label>Estado Activo</label>
                    <select v-model="estado_activo">
                      <option value="N">Nuevo</option>
                      <option value="U">Usado</option>
                      <option value="D">Desuso</option>
                    </select>
                  </div>
                  <div class="col m4">
                    <label>Area Id</label>
                    <input type="text" v-model="areaId">
                  </div>
                </div>                
              </form>
                <div class="row">
                  <button type="submit" class="btn indigo darken-4">AGREGAR ACTIVO<i class="material-icons">add.circle</i></button>
                </div>
                <div class="row">
                  <button type="submit" class="btn indigo darken-4">LISTAR ACTIVOS<i class="material-icons"></i></button>
                </div>
              </div>
              <div class="row">
                <div class="col m12">
                  <table class="table bofrdered striped">
                    <thead>
                      <tr>
                        <th>Tipo</th>
                        <th>Marca</th>
                        <th>Modelo</th>
                        <th>Estado</th>
                        <th>Área Id</th>
                        <th>Eliminar</th>
                        <th>Editar</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tbody>
                        <tr v-for="activo in activos" v-bind:key="activo">
                          <td>{{activo.tipo}}</td>
                          <td>{{activo.marca}}</td>
                          <td>{{activo.modelo}}</td>
                          <td>{{activo.estado}}</td>
                          <td>{{activo.areaId}}</td>
                        </tr>
                      </tbody>
                    </tbody>
                  </table>
                </div>
              </div>
              <h3>Registro de Areas</h3>
              <div class="row">
                <div class="col m12 card-panel">
                  <div class="row">
                    <div class="col m4">
                      <label>Nombre de Area</label>
                      <input type="text" v-model="tipo">
                    </div>
                    <div class="col m4">
                      <label>Nombre de Encargado</label>
                      <input type="text" v-model="tipo">
                    </div>
                    <div class="col m4">
                      <label>Numero Empleados</label>
                      <input type="text" v-model="tipo">
                    </div>
                  </div>
                  <div class="row">
                  <button type="submit" class="btn indigo darken-4">AGREGAR AREA<i class="material-icons">add.circle</i></button>
                  </div>
                  <div class="row">
                  <button type="submit" class="btn indigo darken-4">LISTAR AREA<i class="material-icons"></i></button>
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col m12">
                  <table class="table bofrdered striped">
                    <thead>
                      <tr>
                        <th>Area</th>
                        <th>Encargado</th>
                        <th>Numero_Empleados</th>
                        <th>Eliminar</th>
                        <th>Editar</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tbody>
                        <tr v-for="area in areas" v-bind:key="area">
                          <td>{{activo.Area}}</td>
                          <td>{{activo.Encargado}}</td>
                          <td>{{activo.Numero_Empleados}}</td>
                        </tr>
                      </tbody>
                    </tbody>
                  </table>
          </div>
          </div>
          </div>
          </div>
  </template>

<script>
import M from 'materialize-css'
export default {
  name: 'App',
  data(){
    return{
      tipo:'',
      marca:'',
      modelo:'',
      estado:'',
      estados:[],
      areaId:'',
      activos:[],

      select_instances: []

    }
  },

  mounted()
  {
    var elems = document.querySelectorAll('select');
    this.select_instances = M.FormSelect.init(elems,null);
  },
  methods:{
    agregarProducto()
    {
      var data = {
        tipo: this.tipo,
        marca: this.marca,
        modelo: this.modelo,
        estado: this.estado,
        areaId: this.areaId
      };
      this.productos.push(data);
      this.tipo='';
      this.marca='';
      this.modelo='';
      this.estado='';
      this.areaId='';
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

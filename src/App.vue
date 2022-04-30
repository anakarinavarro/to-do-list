<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-6 my-5">
        <h1 class="text-center my-5">Crea una nueva Tarea</h1>
        <div class="form-group row">
           <label for="inputPassword" class="col-sm-2 col-form-label">Tarea:</label>
           <div class="col-sm-10 d-flex flex-row">
            <input v-model="nuevaTarea" type="text" class="form-control" placeholder="Ingresa una tarea">
            <button @click="agregarNuevaTarea" class="btn btn-secondary ml-3 ">Ingresar</button>
          </div>
       </div>
       <div>
              <h2 class="text-center my-5">Lista</h2>
              <ul class="list-group">
                <li class="list-group-item d-flex align-items-center justify-content-between" v-for="(tarea, index) of tareas" :key="index">
                  {{index + 1}} - {{tarea}} 
                  <button @click="tareas.splice(index,1)" type="button" class="btn btn-link ml-3 eliminar">
                    Eliminar
                    </button>
                    </li>
              </ul>
            </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: ()=>({
    nuevaTarea:"",
    tareas: []
  }),
  methods:{
    agregarNuevaTarea(){
      this.tareas.unshift(this.nuevaTarea)
      this.nuevaTarea = "";
    }

  }
}
</script>

<style>
.eliminar{
  color: red;
}
</style>
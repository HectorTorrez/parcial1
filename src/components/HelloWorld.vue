<template>
  <div class=" ">
    <h1 class="mb-3">{{ msg }}</h1>
   
   <form class="d-flex align-items-start w-100">
  <div class="mb-3 w-25 ms-3 ">
    <label for="exampleInputEmail1" class="form-label">Nombre</label>
    <input type="text" v-model="Nombre" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Ingresa tu Nombre"  v-on:keyup.enter="agregarUsuario">
    
  </div>
  <div class="mb-3 w-25 ms-3 "> 
    <label for="exampleInputPassword1" class="form-label">Apellido</label>
    <input type="text" v-model="Apellido" class="form-control" id="exampleInputPassword1" placeholder="Ingresa tu Apellido"  v-on:keyup.enter="agregarUsuario">
  </div>
  <div class="mb-3 w-25 ms-3 ">
    <label for="exampleInputPassword1" class="form-label">Codigo</label>
    <input type="text" v-model="Codigo" class="form-control" id="exampleInputPassword1" placeholder="Ingresa tu Codigo"  v-on:keyup.enter="agregarUsuario">
  </div>
  <div class="mb-3 w-25 ms-3 ">
    <label for="exampleInputPassword1" class="form-label">Edad</label>
    <input type="number" v-model="Edad" class="form-control" id="exampleInputPassword1" placeholder="Ingresa tu Edad" v-on:keyup.enter="agregarUsuario">
  </div>
  <div class="mb-3 w-25 ms-3 ">

<b-button @click. ="agregarUsuario()" variant="btn btn-success  ms-3 mb-2 px-3" > Agregar Usuarios</b-button>
<b-button @click="Nombre='', Apellido='', Codigo='', Edad=''" block variant="outline-danger ms-3 mb-2  px-3" >LIMPIAR CELDAS</b-button>
  </div>
  

</form>

<b-button @click="elimiartodo(index)" class="btn btn-danger w-100 right  mb-2  px-3" >ELIMINAR TODOS LOS REGITROS</b-button>
    <table class="table">
  <thead>
    <tr>
      <th scope="col">Hombre</th>
      <th scope="col">Apellido</th>
      <th scope="col">Codigo</th>
      <th scope="col">Edad</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Héctor</td>
      <td>Torrez</td>
      <td>SMIS080319</td>
      <td>21</td>
      <td><b-icon icon="lock-fill"></b-icon></td>
    </tr>
    <tr v-for="(usuario, index) in usuarios" v-bind:key="usuario">

      <td> {{usuario.Nombre}}</td>
      <td>{{usuario.Apellido}}</td>
      <td>{{usuario.Codigo}}</td>
      <td>{{usuario.Edad}}</td>

<!-- eliminar una celda -->
      <td><b-icon icon="trash-fill" @click="eliminar(index)"></b-icon></td>
      
      
    </tr>
  </tbody>
    </table>





  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      Nombre: '',
      Apellido: '',
      Codigo: '',
      Edad:'',
      usuarios:[]
    }
  },
  methods: {
    agregarUsuario  (){
      var data ={
        Nombre: this.Nombre,
      Apellido: this.Apellido,
      Codigo: this.Codigo,
      Edad: this.Edad
      };
      this.usuarios.push(data);
      this.Nombre='',
      this.Apellido='',
      this.Codigo='',
      this.Edad=''
      


      
      },
      eliminar(index){
        this.usuarios.splice(index, 1);
      },
    elimiartodo(index){
      this.usuarios.splice(index)
    }
    }
  }
  

</script>



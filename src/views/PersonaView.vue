<template>
  <h1>Lista de personas</h1>
  <p>{{personas}}</p>
  <table border="1">
    <tr>
      <td>NOMBRE</td>
      <td>EDAD</td>
      <td>ACCION</td>
    </tr>
    <tr v-for="p in personas" :key="p">
      <td>{{p.nombre}}</td>
      <td></td>
      <td></td>
    </tr>
  </table>
</template>

<script>
export default {
  data(){
        return {
            personas: []
        }
  },
  mounted(){
       fetch('http://127.0.0.1:8000/api/persona')
        .then(response => response.json())
        .then((json) => {
            console.log(json)
            this.personas = json
        }) 
  }
}
</script>

<style>

</style>
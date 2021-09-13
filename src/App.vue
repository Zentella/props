<template>
  <div id="App">
    <form>
      <label for="listado">Tarea</label>

      <input type="text"     v-model="texto"  id="listado"   placeholder="ingresa nueva tarea"/>
      <div v-if="texto">
      <button class="btn" type="button" @click.prevent="guardar">Añade</button>
      </div>
    </form>
    
    
    <Listado :lista="lista" @eliminarItem="eliminarItem" />
    
  </div>
</template>

<script>
import Listado from "./Listado.vue";

export default {
  name: "App",
  components: {
    Listado,
  },

  data() {
    return {
      lista: [],
      texto: '',
    };
  },

  methods: {
    guardar() {
      this.lista.push(this.texto);
      this.texto = '';               

    },

    eliminarItem(index) {
      this.lista.splice(index, 1);
    },
  },
};
</script>

<style>
#App {
  padding: 40px 400px;
}
button {
  border-radius: 12%;  
  border: 1px solid black;  
  margin: 2px;
}
button:hover {
    border: 4px solid rgb(122, 167, 204);

}
.btn {
  position: absolute;
    margin: -30px 0 0 300px;
  }
</style>
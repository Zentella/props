<template>
  <div>
      <ul>
        <li v-for="(item, index) in lista" :key="index">
          {{ lista[index] }}

          <button @click="eliminar(index)">eliminar</button>
        </li>
      </ul>
  </div>
</template>

<script>
export default {

  name: "Listado",
  props: {
    lista: [],
    
  },

  methods: {
    eliminar(index) {
      this.$emit("eliminarItem", index);
    },
  },
};
</script>



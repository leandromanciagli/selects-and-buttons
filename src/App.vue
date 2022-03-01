<template>
  <div id="app">
    <generic-select @onSelected="setName" :options="names" selectName="names" selectId="names"/>
    <generic-select @onSelected="setSurname" :options="surnames" selectName="surnames" selectId="surnames"/>
    <button :disabled="validateDisableButton" @click="alertUser">Aceptar</button>
  </div>
</template>

<script>
import GenericSelect from './components/GenericSelect.vue'

export default {
  name: 'App',

  components: {
    GenericSelect
  },

  data () {
    return {
      names: [ 'Leonardo', 'Julia', 'Carla', 'Tom' ],
      surnames: [ 'Scamozo', 'Gomez', 'Di Nardi' ],
      nameSelected: null,
      surnameSelected: null
    }
  },

  methods: {
    alertUser(){
      alert('¡Se clickeó!')
    },

    setName(name){
      console.log(name);
      this.nameSelected = name
    },

    setSurname(surname){
      this.surnameSelected = surname
    }
  },

  computed: {
    validateDisableButton() {
      return !((this.nameSelected != null) && (this.surnameSelected != null))
    }
  },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

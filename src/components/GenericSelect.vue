<template>
  <div>
    <select :name="selectName" :id="selectId" v-model="optionSelected" @change="$emit('onSelected', optionSelected)">
      <option selected disabled>Seleccione una opción</option>
      <option :value="option" v-for="option in options" :key="option">{{ option }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'GenericSelect',

  props: {
   options: { type: Array },
   selectName: { type: String },
   selectId: { type: String },
  },

  data () {
    return {
      optionSelected: null
    }
  },

}
</script>

<style scoped>

</style>

<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <AssignmentsComp />
  <AssignmentCreate />
  <ListComp />
  <hr />

  <CreateCharacter />
</template>

<script>

import AssignmentsComp from "./components/AssignmentsComp.vue";
import AssignmentCreate from "./components/AssignmentCreate.vue"

import ListComp from "./components/ListComp.vue"

import CreateCharacter from "./components/CreateCharacter.vue"

export default {
  name: 'App',

  components: {
    AssignmentsComp,
    AssignmentCreate,
    ListComp,

    CreateCharacter
  },

  data() {
    return {
        
    }
  },

  methods: {
    
  }
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

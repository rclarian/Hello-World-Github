<template>
  <div class="app">
    <p>{{ name }} - {{age}}</p>
    <button @click="changeName('Ryan')">Change name</button>
    <button @click="changeAge('29')">Change age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from 'vue';


export default defineComponent({
  name: 'App',
  components: {},
  setup(){
    const state = reactive({
      name: 'Link',
      age: 25 as string | number
    })

    state.name = '999' //cannot change type
    state.age = 26

    return { ...toRefs(state) }
  },
  methods: {
    changeName(name: string){
      this.name = name
      return name
    },
    changeAge(age: number | string){
      this.age = age
      return age
    }
  }



});
</script>

<style>

</style>

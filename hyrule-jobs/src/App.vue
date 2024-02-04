<template>
  <div class="app">
    <JobsList :jobs="jobs" />
    
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobsList from './components/JobsList.vue';
import Job from './types/Job'



export default defineComponent({
  name: 'App',
  components: {JobsList},
  setup(){
    
    const jobs = ref<Job[]>([
      { title: 'Farm Worker', location: 'Lon Lon Ranch', salary: 30000, id: '1' },
      { title: 'Quarryman', location: 'Death Mountain', salary: 40000, id: '2' },
      { title: 'Flute Player', location: 'The Lost Woods', salary: 35000, id: '3' },
      { title: 'Fisherman', location: 'Lake Hylia', salary: 21000, id: '4' },
      { title: 'Prison Guard', location: 'Gerudo Valley', salary: 32000, id: '5' }
    ])
    return { jobs }
  },
  methods: {
    // changeName(name: string){
    //   this.name = name
    //   return name
    // },
    // changeAge(age: number | string){
    //   this.age = age
    //   return age
    // }
  }



});
</script>

<style>

</style>

<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">Orber by Title</button>
    <button @click="handleClick('salary')">Orber by Salary</button>
    <button @click="handleClick('location')">Orber by Location</button>
      </div>
    </header>
    <JobsList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import JobsList from './components/JobsList.vue';
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'


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

    const order = ref<OrderTerm>('title');
    const handleClick = (term: OrderTerm) => {
      order.value = term;

    }

    return { jobs, handleClick, order }
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
header {
  text-align: center;
}
header .order{
  margin-top: 20px;
}
button{
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}

</style>

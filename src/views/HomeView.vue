<template>
  <div class="app">
    <JobsListVue :jobs="jobs" :order="order"/>  
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Job from '@/types/Job';
import OrderTerm from '@/types/OrderTerm';
import JobsListVue from '../components/JobsList.vue';

export default defineComponent({
  name: 'HomeView',
  components: { JobsListVue },
	setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])
	
		
		const order = ref<OrderTerm>('title')
		
    return { jobs, order }
  }
});
</script>

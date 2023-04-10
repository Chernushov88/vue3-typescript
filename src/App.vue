<template>
  <router-view>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  </router-view>
  <div class="app">
<!--    <p>{{ name }} - {{ age }}</p>-->
<!--    <button @click="changeName('Zelda')">change name</button>-->
<!--    <button @click="changeAge('50')">change age</button>-->
    <table border-collapse="collapse" border="1" cellpadding="3">
      <tbody>
      <tr v-for="item in jobs" :key="item.title">
        <td v-for="elem in item" :key="elem"> {{elem}} </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import Job from '@/types/Job'

export default defineComponent({
  name: 'App',
  components: {},
  setup() {
    /*const state = reactive({
      name: 'Link',
      age: 25 as number | string
    })
    state.name = '999' // cannot change type
    state.age = '26'
    return {...toRefs(state)}*/

    /*const name = ref('lift')
    const age = ref<number | string>(25)
    age.value = 30
    return {name, age}*/
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'lon lon ranch', salary: 30000, id: '1' },
      { title: 'quarryman', location: 'death mountain', salary: 40000, id: '2' },
      { title: 'flute player', location: 'the lost woods', salary: 35000, id: '3' },
      { title: 'fisherman', location: 'lake hylia', salary: 21000, id: '4' },
      { title: 'prison guard', location: 'gerudo valley', salary: 32000, id: '5' }
    ])
    return { jobs }
  },
  methods: {
    /*changeName(name: string) {
      this.name = name
      return name
    },
    changeAge(age: number | string) {
      this.age = age
      return age
    }*/
  }
});
</script>
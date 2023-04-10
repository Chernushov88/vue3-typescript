<template>
	<nav>
		<router-link to="/">Home</router-link> |
		<router-link to="/about">About</router-link>
	</nav>	
	<header>
		<div class="title">
			<img src="../assets/heart.svg" alt="site logo">
			<h1>Hyrule Jobs</h1>
		</div>
		<div class="order">
			<button @click="handleClick('title')">Order by title</button>
			<button @click="handleClick('salary')">Order by salary</button>
			<button @click="handleClick('location')">Order by location</button>
		</div>
	</header>
</template>
<script lang="ts">
import { defineComponent, PropType, ref } from "vue";
import OrderTerm from '@/types/OrderTerm'
import Job from '@/types/Job'

export default defineComponent({
	props: {
		jobs: {
      type: Array as PropType<Job[]>,
      required: true
    },
		order: {
      type: String as PropType<OrderTerm>,
      required: true
    }
	},
  setup(props) {
		const order = ref<OrderTerm>('title')
		const handleClick = (term: OrderTerm) => {
			console.log('props', props);
			
			//props.order.value = term
		}
		return {handleClick}
	},
});
</script>
<style>
header .title{
    display: flex;
    justify-content: center;
  }
  header img {
    width: 60px;
    margin-right: 20px;
  }
  header h1 {
    font-size: 3em;
  }
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
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
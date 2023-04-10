<template>
	<div class="lob-list">
		<ul>
			<li v-for="job in jobs" :key="job.id">
				<h2>{{ job.title }} in {{ job.location }}</h2>
				<div class="salary">
					<p>{{ job.salary }} rupees</p>
				</div>
				<div class="description">
					<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum reiciendis ad, neque, odio dignissimos reprehenderit earum ab quod nesciunt amet consequuntur? Quae harum laborum delectus molestias neque, officiis magni sint.</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '@/types/Job'

export default defineComponent({
	props: {
		jobs: {
			required: true,
			type: Array as PropType<Job[]>
		}
	}
})
</script>

<style scoped>

</style>

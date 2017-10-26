<template>
	<div id='movie-filter'>
		<h2> Filter Results </h2>
		<h3>By Time of day</h3>
		<div class="filter-group">
			<check-filter v-for="time in times" :title="time" category="time" v-on:check-filter="checkFilter"></check-filter>
		</div>
		<h3>By Genre</h3>
		<div class="filter-group">
			<check-filter v-for="genre in genres" :title="genre" category="genre" v-on:check-filter="checkFilter"></check-filter>
		</div>
	</div>
</template>

<script>
import genres from '../util/genres.js';
import times from '../util/times.js';
import CheckFilter from './CheckFilter.vue';

	export default {
		data() {
			return {
				genres,
				times
			}
		},
		methods: {
			checkFilter (category, title, checked) {
				this.$emit('check-filter',category, title, checked);
			}
		},
		components: {
			CheckFilter
		}
	}
	
</script>
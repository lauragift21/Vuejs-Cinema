<template>
	<div id='movie-list'>
		<div v-for="movie in filteredMovies" class="movie"> {{ movie.title }} </div>
	</div>
</template>
<script>
import genres from '../util/genres.js';
	export default {
			data() {
				return {
					movies: [
						{title: 'Homecoming', genre: genres.CRIME},
						{title: 'Kingsmen', genre: genres.ANIMATION},
						{title: 'Gentleman', genre: genres.ANIMATION},
						{title: 'Geostorm', genre:genres.DRAMA}
					]	
				}
			},
		props: ['genre', 'time'],
		// methods: {
		// 	moviePassesGenreFilter(movie) {
		// 	if (this.genre.length) {
		// 	return true;
		// } else {
		// 	return this.genre.find(genre => movie.genre === genre);
		// }

		// 	}
		// },
		computed: {
			filteredMovies() {
				return this.movies();
			}
		}
		

	}
</script>
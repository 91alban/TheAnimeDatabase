<template>
<header>
    <h1>The<strong>Anime</strong>Database</h1>

    <form class="search-box" @click="SearchAnime" @submit.prevent="HandleSearch">
		<input 
            type="search"
            class="search-field"
            placeholder="Search for an anime..."
            required 
            v-model="search_query"/>
		</form>
</header>
</template>

<script>
import { ref } from 'vue';	

export default {
    setup() {
		const search_query = ref("");
		const animeList = ref([]);
		const HandleSearch = async () => {
			animeList.value = await fetch(`https://api.jikan.moe/v3/search/anime?q=${search_query.value}`)
				.then(res => res.json())
				.then(data => data.results);
				console.log(animeList.value);
		}
		return {
			search_query,
			animeList,
			HandleSearch
		}
	},
    methods: {
		// SearchAnime (event) {
		// 	this.$emit('clicked', 'this.animeList')
		// }
        // HandleSearch() {
        //     this.$emit('animeList', this.animeList)
        // }
    }
}
</script>
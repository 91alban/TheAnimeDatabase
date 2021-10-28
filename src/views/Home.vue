<template>
  <div class="home">
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
    <MainBody 
			:animeList="animeList"
    />
  </div>
</template>

<script>
import { ref } from 'vue';	

import MainBody from '@/components/MainBody.vue'

export default {
  name: 'Home',
  components: {
    MainBody,
  },
  setup() {
		const search_query = ref("");
		const animeList = ref([]);
		const HandleSearch = async () => {
			animeList.value = await fetch(`https://api.jikan.moe/v3/search/anime?q=${search_query.value}`)
				.then(res => res.json())
				.then(data => data.results);
				// console.log(animeList.value);
		}
		return {
			search_query,
			animeList,
			HandleSearch
		}
	},
}
</script>

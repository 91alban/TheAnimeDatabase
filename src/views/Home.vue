<template>
  <div class="home">
    <header>

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

// <style lang="scss" scoped>
// header {
// 	padding-bottom: 100px;
	
// 	.search-box {
// 		display: flex;
// 		justify-content: center;
// 		padding-left: 30px;
// 		padding-right: 30px;
// 		.search-field {
// 			appearance: none;
// 			background: none;
// 			border: none;
// 			outline: none;
// 			background-color: #F3F3F3;
// 			box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.15);
// 			display: block;
// 			width: 100%;
// 			max-width: 600px;
// 			padding: 15px;
// 			border-radius: 8px;
// 			color: #313131;
// 			font-size: 20px;
// 			transition: 0.4s;
// 			&::placeholder {
// 				color: #AAA;
// 			}
// 			&:focus, &:valid {
// 				color: #FFF;
// 				background-color: #313131;
// 				box-shadow: 0px 0px 0px rgba(0, 0, 0, 0.15);
// 			}
// 		}
// 	}
// }
// </style>
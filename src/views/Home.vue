<template>
  <div class="home w-full antialiased">
    <header>
		<div class="bg-indigo-600">
    	<form class="search-box" @click="SearchAnime" @submit.prevent="HandleSearch">
			<div class="relative flex items-center max-w-md mx-auto overflow-hidden text-center mb-5">
				<input 
					type="search"
					class="w-full h-12 px-6 py-2 font-medium text-indigo-800 focus:outline-none border-gray-900"
					placeholder="Search for an anime..."
					required 
					v-model="search_query"/>
			</div>
		</form>
		</div>
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
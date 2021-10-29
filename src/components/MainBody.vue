<template>
    <main>
		<div class="cards">
			<Card 
				v-for="anime in animeList" 
				:key="anime.mal_id" 
				:anime="anime" />
		</div>
	</main>
</template>

<script>
import Card from '../components/Card.vue';

export default {
    props: ['animeList'],
    setup() {
        
    },
    components: {
		Card
	},
}
</script>

<style lang="scss" scoped>
main {
	max-width: 1200px;
	margin: 0 auto;
	padding-left: 20px;
	padding-right: 20px;
	.cards {
		display: flex;
		flex-wrap: wrap;
		margin: 0 -12px;
	}
}
</style>
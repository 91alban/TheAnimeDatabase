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
    
    setup() {
        
    },
    components: {
		Card
	},
}
</script>
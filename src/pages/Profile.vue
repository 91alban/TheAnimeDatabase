<template>
    <div>
        {{ anime.title }}
    </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
// import env from '@/env.js';

export default {
    setup() {
        const anime = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`https://api.jikan.moe/v3/anime/${route.params.id}`)
            .then(response => response.json())
            .then(data => {
                anime.value = data;
            });
        });

        return{
            anime
        }
    }
    
}
</script>
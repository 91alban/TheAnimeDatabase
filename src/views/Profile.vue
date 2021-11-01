<template>
        <main>
            <div class="row m-8">
                <div class="left col-lg-4">
                    <div class="photo-left">
                        <img class="photo" :src="anime.image_url"/>
                    </div>
                </div>
            </div>
            <Characters 
                :anime="anime"
            />
        </main>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import Characters from '../components/Characters.vue';

export default {
    components:{
        Characters
    },
    setup() {
        const anime = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`https://api.jikan.moe/v3/anime/${route.params.id}`)
            .then(response => response.json())
            .then(data => {
                anime.value = data;
                console.log(anime);
            });
        });

        return{
            anime
        }
    }
    
}
</script>


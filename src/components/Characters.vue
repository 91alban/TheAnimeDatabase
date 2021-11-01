<template>
    <div class="relative py-20 overflow-hidden bg-white">
        <span class="absolute top-0 right-0 flex flex-col items-end mt-0 -mr-16 opacity-60">
            <span class="container hidden w-screen h-32 max-w-xs mt-20 transform rounded-full rounded-r-none md:block md:max-w-xs lg:max-w-lg 2xl:max-w-3xl bg-blue-50"></span>
        </span>

        <span class="absolute bottom-0 left-0"></span>

        <div class="relative px-16 mx-auto max-w-7xl">
            <p class="font-medium tracking-wide text-blue-500 uppercase">{{ anime.title }} Characters</p>
            <h2 class="relative max-w-lg mt-5 mb-10 text-4xl font-semibold leading-tight lg:text-5xl">An incredible team of <br>amazing individuals</h2>
                <div class="grid w-full grid-cols-2 gap-10 sm:grid-cols-3 lg:grid-cols-4">
            <div v-for="character in characters.characters"
                :key="character.mal_id"
                :character="character">
                    <div class="flex flex-col items-center justify-center col-span-1">
                        <div class="relative p-5">
                            <div class="absolute z-10 w-full h-full -mt-5 -ml-5 rounded-full rounded-tr-none bg-blue-50"></div>
                            <img class="relative z-20 w-full rounded-full" :src="character.image_url">
                        </div>
                        <div class="mt-3 space-y-2 text-center">
                            <div class="space-y-1 text-lg font-medium leading-6">
                                <h3>{{character.name}}</h3>
                                <p class="text-blue-600">{{character.role}}</p>
                            </div>
                        </div>
                    </div>
                </div> 
            </div>
        </div>
    </div>
</template>

<script>
import { ref, onBeforeMount } from '@vue/runtime-core';
import { useRoute } from 'vue-router';

export default {
    props: ['anime'],
    setup() {
        const characters = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`https://api.jikan.moe/v3/anime/${route.params.id}/characters_staff`)
            .then(response => response.json())
            .then(data => {
                characters.value = data;
                console.log(characters);
            });
        });

        return {
            characters
        }
    }

}

</script>


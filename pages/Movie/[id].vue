<script setup lang="ts">
import { movies } from "~/composables/useMovie";
import type { Movie } from "~/types/models/Movie";
const route = useRoute();
const movie = ref<Movie | null>(null);
onMounted(() => {
    movie.value = movies.find((movie) => movie.title === route.params.id) || null;

    if(movie.value) {
        useHead({
            title: movie.value.title,
            meta: [
                {
                    name: 'description',
                    content: movie.value.description
                }
            ]
        });
    }
    else {
        useHead({
            title: 'Movie not found',
            meta: [
                {
                    name: 'description',
                    content: 'Movie not found'
                }
            ]
        });
    }
});
</script>
<template>
    <div class="pt-20">
        <div v-if="movie">
            <div class="grid grid-cols-10 justify-center gap-20">
                <div class="cols-span-3"> 
                    <img :src="movie.image" :alt="movie.title" />
                </div>
                <div class="cols-span-7">
                    <h1>{{ movie.title }}</h1>
                </div>

            </div>
         </div>
         <div v-else> Movie Not Found</div>
    </div>
</template>
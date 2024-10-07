<script setup lang="ts">
    import { movies } from "~/composables/useMovie";
</script>
<template>
    <div class="flex flex-col pb-4">
        <div class="border-b"><span>Top 10 Movies</span></div>
        <div class="flex flex-row gap-10 flex-wrap pt-4 px-6">
            <div v-for="(movie, index) in movies">
                <NuxtLink :to="`Movie/${movie.title}`">
                    <MovieCard :key="index" :title="movie.title" :image="movie.image" :description="movie.description"/>
                 </NuxtLink>
            </div>
        </div>
    </div>
</template>
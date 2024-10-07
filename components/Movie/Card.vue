<script setup lang="ts">
const props = defineProps<{
    title: string,
    image: string;
    description: string;
}>();
</script>
<template>
    <div class="flex flex-col items-center  border-b max-w-[6rem] max-h-[12rem] ">
        <div class="flex justify-center border-b overflow-hidden">
            <img :src="props.image" alt="movie" class="h-64 w-[14rem] rounded-sm object-cover  transition-transform duration-300 ease-in-out transofrm hover:scale-110">
        </div>
        <div class="flex flex-col py-2 w-full">
            <p class="truncate w-full">{{ props.title }}</p>
            <p class="truncate w-full">{{ props.description }}</p>
        </div>

    </div>
</template>
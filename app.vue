<script setup lang="ts">
  useHead({
    title: 'Flix | Movie review',
    /*link: [
      {
        rel: 'icon',
        type: 'image/x-icon',
        href: '/favicon.ico'
      }
    ]*/
    meta: [
      {
        name: 'description',
        content: 'Flix is a movie review app'
      }
    ]
  });
  
</script>
<template>
  <div>
   <NuxtLayout>  
      <NuxtPage />
   </NuxtLayout>
  </div>
</template>

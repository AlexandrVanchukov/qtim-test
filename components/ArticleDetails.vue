<template>
    <div>
        <h1 class='title'>{{article.title}}</h1>
        <img :src='article.image' alt="">
        <h3>About</h3>
        <p>{{article.description}}</p>
    </div>
</template>

<script setup lang='ts'>
   const { article } = defineProps(['article'])
</script>

<style scoped>

</style>
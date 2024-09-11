<template>
    <div>
        <img :src="article.image" alt="">
        <p> {{article.title}}</p>
        <NuxtLink :to='`/articles/${article.id}`'>Read more</NuxtLink>
    </div>
</template>

<script setup lang='ts'>
    const { article } = defineProps(['article'])
</script>

<style lang="scss" scoped>

</style>
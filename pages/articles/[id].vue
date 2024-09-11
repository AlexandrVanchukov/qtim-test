<template>
    <div>
        <ArticleDetails :article='article'/>
    </div>
</template>

<script setup lang='ts'>

    const { id } = useRoute().params;

    const uri = 'https://6082e3545dbd2c001757abf5.mockapi.io/qtim-test-work/posts/' + id;

    const { data: article } = await useFetch(uri);

</script>

<style lang="scss" scoped>

</style>
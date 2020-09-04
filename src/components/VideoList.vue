<template>
    <ul>
        VideoList
        {{videos}}        
    </ul>
</template>

<script>
export default {
    name: 'VideoList',
    props: {
        videos: Array
    }
};
</script>

<style>
</style>
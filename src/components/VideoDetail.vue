<template>
    <div v-if="video">
        <div class="details">
            <h4>{{ video.snippet.title}}</h4>
            <p>{{ video.snippet.description }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name:'VideoDetail',
    props: ['video']
}
</script>
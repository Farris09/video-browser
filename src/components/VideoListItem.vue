<template>
  <li class="list-group-item">
    <img :src="video.snippet.thumbnails.default.url" />
    {{ video.snippet.tittle }}
  </li> 
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video']  
};
</script>
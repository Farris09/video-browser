<template>
  <li>
    {{ video.snippet.tittle }}
  </li> 
</template>

<script>
export default {
  name: 'VideoListItem',
  props: ['video']  
};
</script>
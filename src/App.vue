<template>
    <div>
       <SearchBar v-on:termChange="onTermChange"></SearchBar>
  <!--      <VideoList :videos="videos"></VideoList>
 -->    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
//import VideoList from './components/VideoList';

//const API_KEY = 'AIzaSyBjj_K6lIvTpH8U4yd69G6OLwiFgExXbOk';
const API_KEY_TEAM = 'AIzaSyBHFoz1az9JPzxoOe3PFPXsMjho_y1ZvqM'

export default {
 name: 'App',
 components: {
     SearchBar,
     //VideoList
 },
 data() {
     return{ videos: [] };
 },
 methods: {
     onTermChange (searchTerm) {
         axios
          .get('https://www.googleapis.com/youtube/v3/search', {
           params: {
               key: API_KEY_TEAM,
               type: 'video',
               part: 'snippet',
               q : searchTerm
           }
       })
       .then (response => {
           this.videos = response.data.items;
           console.log(this.videos)
       });
     }
 }   
};
</script>
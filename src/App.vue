<template>
    <div>
       <SearchBar @termChange="onTermChange"></SearchBar>
       <VideoList></VideoList>
    </div>
</template>

<script>
import axios from 'axios';
import SearchBar from './components/SearchBar';
import VideoList from './components/VideoList';

const API_KEY = 
'AIzaSyBjj_K6lIvTpH8U4yd69G6OLwiFgExXbOk';

export default {
 name: 'App',
 components: {
     SearchBar,
     VideoList
 },
 data() {
     return{ videos: [] };
 },
 methods: {
     onTermChange (searchTerm) {
         axios
          .get('http://www.googleapis.com/youtube/v3/search', {
            params: {
               key: API_KEY,
               type: 'video',
               part: 'snippet',
               q: searchTerm
           }
       })
       .then (response => {
           this.videos = response.data.items
       });
     }
 }   
};
</script>
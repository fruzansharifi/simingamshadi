<template>
  <div id="app">

    <h1>{{title_place}}</h1>
    <HelloWorld/>
    <Slider :images="images"/>
    <gallery :images="images"/>
    <Comment v-bind:comments="comments"  :images="images"
    :stars="stars" 
    :rate="rate"
    :avg="avg"
     v-on:new-comment="newComment"
     />
    <Discription :description="description"/>
    <AboutUs/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Slider from './components/Slider.vue'
import gallery from './components/gallery.vue'
import Discription from './components/Discription.vue'
import Comment from './components/Comment.vue'
import AboutUs from './components/AboutUs.vue'
import axios from "axios";

export default {
  name: 'App',
  components: {
    HelloWorld,
    Slider,
    AboutUs,
    gallery,
    Comment,
    Discription
  },
  data(){
    return{
      avg:'',
      rate:'',
      stars:[
        {rate:'1', id:"1"},
        {rate:'2', id:"2"},
        {rate:'3', id:"3"},
        {rate:'4', id:"4"},
        {rate:'5', id:"5"}],
      comments:[],
      title_place:'',
      description :'',
      images:[]
      /* {id:'1',nazar:"hiiii",rate:'0'}]*/
    }
    },
     mounted:function(){
      this.fetchData();  
  },
 methods:{
   newComment: function(newComment){
     axios.post('https://jsonplaceholder.typicode.com/comments/',newComment)
     .then(res => this.comments.push(res.data))
     .catch(err => console.log(err));
   },
   created:function(){
     axios.get('https://jsonplaceholder.typicode.com/comments?_limit=5')
      .then(res => this.comments =res.data)
      .catch(err => console.log(err));
   },
   avage: function(){
     for(let i=0 ; i<this.comments.length;i++){
      this.avg+=this.comments.rate[i];
     }
     this.avg/=this.comments.length;
     this.$emit("avg",this.avg);
     
   },
   fetchData: function(){
     var url = 'https://sharifi.liara.run';
     var partUrl = '/places/view/13';
// var xhr = new XMLHttpRequest();
// xhr.open("POST", url+partUrl, true);
// xhr.setRequestHeader('Content-Type', 'application/json');
// xhr.setRequestHeader('Access-Control-Allow-Origin', '*');
axios.post(url+partUrl).then(res => {
  var data = res.data;
    console.log(data);

  this.title_place = data.title;
  this.description = data.description;
  this.images = data.images;
});

   }
 }
}
</script>

<style>
.hide{
  display: none;
}



#app {
  background-image:  url(assets/background.png ) ;
  background-color: rgb(245, 239, 239);
  
}
#app h1{
  text-align: center;
  text-shadow: 5px 5px 5px rgb(108, 108, 128);
  color: rgb(134, 25, 25);
  padding: 10px 30%;
  background-color: rgb(209, 189, 180);
  font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
}
</style>

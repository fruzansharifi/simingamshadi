<template>
  <div>
      
      <div class="slider">
          <span class="left-slider icon-left-open" @click="slider()"></span>
          <img :src="'https://sharifi.liara.run'+images[0].path" alt="" @click="showComment()" height="300px" width="300px">
          <span class="right-slider icon-right-open" @click="slider()"> </span>
      </div>
      <div class="footer-slider">
          <span>
              <button class="go-to-gallery" @click="showGallery()"> go to gallery</button>
          </span>
          
      </div>
  </div>
</template>
<script>
export default {
    name:"Slider",
    methods:{
        showComment(){
            document.querySelector(".comment").classList.remove("hide");
        },
        showGallery(){
            document.querySelector(".gallery").classList.toggle("hide");
        }
    },
    props:['images']
}
</script>

<style scoped>
    @font-face{
        font-family: my-font;
        src:url('../assets/css/fontello.css')
    }
    .slider{
            position: relative;
            z-index: 1;
            margin: 10px 10%;
        }
    .slider img{
        border: rgb(132, 155, 154) solid;
        border-radius: 10px;
        z-index: 1;
        margin: auto;
        display: block;
        right: 0px;
        top: 0px;
    }
     .slider :hover{
        cursor: pointer;
        opacity: 0.8;
        background-color: rgb(185, 185, 216) !important;
    }

    .left-slider{
        color: rgb(15, 15, 75);
        background-color: rgba(158, 152, 153,0.7);
        z-index: 2;
        position: absolute;
        top: 150px;
        left: 30px;
        padding: 4px;
        border-radius: 4px;
        font-size: 1.5em;
    }
    .right-slider{
        color: rgb(15, 15, 75);
        background-color: rgba(158, 152, 153, 0.7);
        z-index: 2;
        position: absolute;
        top: 150px;
        right: 30px;
        padding: 4px;
        border-radius: 4px;
        font-size: 1.5em;
    }
    .footer-slider{
        margin: 0% 20%;
        
    }
    .go-to-gallery{
    padding: 4px 1.1em;
    cursor: pointer;
    border-radius: 10%;
    border: rgb(238, 219, 247) 2px solid;
    background-image: none;
    font-size: 14px;
    background-color: rgb(67, 60, 68);
    color: white;
    position: relative;
    top: 9px;
    margin-bottom: 10px;
  }
        
    .go-to-gallery:hover{
    background-color: rgba(75, 71, 71, 0.7);
        }
    
    
</style>

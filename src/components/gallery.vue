<template>
    <div  class="gallery hide">
        <span class="icon-cancel" @click="unshowGallery()"></span>
        <div>
            <ul>
            <li class="img" v-for="image in images" :key="image.id"  >
                <img :src="'https://sharifi.liara.run'+image.path" alt="00" width="100px" height="100px">
            </li>
            <!-- <li class="img">
                <img src="../assets/11.jpg" alt="11" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/22.jpg" alt="22" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/33.jpg" alt="33" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/44.jpg" alt="44" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/55.jpg" alt="55" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/66.jpg" alt="66" width="100px" height="100px">
            </li>
            <li class="img">
                <img src="../assets/77.jpg" alt="77" width="100px" height="100px">
            </li> -->
        </ul>
        </div>
    <button type="submit" class="add-img">افزودن عکس</button>   
    </div>
  
</template>

<script>
export default {
    name:"gallrty",
    methods:{
        unshowGallery(){
            document.querySelector(".gallery").classList.add("hide");
        }
    },
    props:['images']


}
</script>

<style>
    @font-face{
        font-family: my-font;
        src:url('../assets/css/fontello.css')
    }
    .gallery{
        background-color: rgba(2, 1, 1, 0.7);
        margin: 10px 10%;
    }
    .icon-cancel{
      border-radius: 5px;
      margin-top: 5px;
      margin-right:10px ;
      float: right;
      font-size: 1.3em;
      color: rgb(56, 54, 54);
      background-color: rgba(255, 0, 0, 0.8);
      cursor: pointer;
    }
    .icon-cancel:hover{
      background-color: rgba(255, 0, 0, 0.5) !important;
    }
    .img{
        margin-top: 30px;
        display: inline-block;
        grid-template-columns: auto auto auto;
        padding: 10px;
    }
    ul li{
        padding: 20px;
    }
    .gallery ul li:hover{
        transform:scale(3) ;
        transition-delay: 150ms;
        z-index: 2;
    }
    img{
        
        border: black solid 1px; 
        border-radius: 4px;
    }
    .add-img{
        padding: 2px 1.1em;
        margin: 0px 0px 10px 10px;
        border-radius: 10%;
        border: rgb(49, 41, 12) 2px solid;
        background-image: none;
        font-size: 14px;
        background-color: rgb(247, 227, 14);
        color: rgb(84, 85, 54);
    }
    .add-img:hover{
         background-color: rgba(247, 227, 14, 0.8);
    }
</style>
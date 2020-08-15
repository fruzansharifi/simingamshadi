<template>
  <div class="about-us">
      <h2>ABOUT us</h2>
      <button type="submit"
       class="front-developer developer"
       @click="unhidefront()"
       >front developer</button>
      <button type="submit"
       class="back-developer developer"
       @click="unhideback()"
       >back developer</button>
      <div class="front hiide ">
          front developer<br>
          name:simin gamshadi<br>
          email:<a href="simin.gamshadi97@gmail.com">"simin.gamshadi97@gmail.com"</a>
          
      </div>
      <div class="back  hiide">
          back developer<br>
          name:forouzan sharifi<br>
          email:<a href="forouzan.sharifi2020@gmail.com">"forouzan.sharifi2020@gmail.com"</a>
      </div>
  </div>
</template>

<script>
export default {
  name: 'AboutUs',
  methods:{
      unhidefront: function(){
          document.querySelector(".front").classList.toggle("hiide");
          document.querySelector(".back").classList.add("hiide");
      },
       unhideback: function(){
          document.querySelector(".back").classList.toggle("hiide");
          document.querySelector(".front").classList.add("hiide");
      }
  }
}
</script>
<style scoped>
    @font-face{
        font-family: my-font;
        src:url('../assets/css/fontello.css')
    }
    .hiide{
        visibility: hidden;
    }
    .about-us{
        width: 100%;
        height: 200px;
        background-color: rgba(0, 0, 0,0.5);
        
        text-align: center;
    }
    .about-us h2{
        
        margin: 10px ;
         text-align: center;
         text-shadow: 8px 8px 8px rgba(99, 68, 68,0.7);
         color: rgb(36, 34, 34);
         padding: 10px 30%;
         font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    }
    .about-us h2:hover{
        text-align: center;
         text-shadow: 8px 8px 8px rgba(99, 68, 68,1);
         color: rgb(15, 15, 15);
         padding: 10px 30%;
         background-color: rgba(0, 0, 0,o.8) !important;
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    }
    .developer{
        margin: 10px;
        padding: 4px 1.1em;
        cursor: pointer;
        border: rgb(238, 219, 247) 1px solid;
        background-image: none;
        font-size: 14px;
        background-color: rgb(67, 60, 68);
        color: white;
    }
    .developer:hover{
        margin: 10px;
        padding: 4px 1.1em;
        cursor: pointer;
        border: rgb(238, 219, 247) 1px solid;
        background-image: none;
        font-size: 14px;
        background-color: rgb(53, 48, 48);
        color: white;
        transform: scale(1.1);
    }
    .front{
        margin: 10px 10%;
        padding: 10px 0px;
        background-color: rgba(251, 245, 234,0.3);
        border: rgb(110, 110, 105) solid 1px;
    }
    .back{
        margin: 10px 10%;
        padding: 10px 0px;
        background-color: rgba(251, 245, 234,0.3);
        border: rgb(110, 110, 105) solid 1px;
        position: relative;
        bottom: 86px;
    }
</style>

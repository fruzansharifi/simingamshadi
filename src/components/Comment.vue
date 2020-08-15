<template>
<div class="comment hide">
  
  <span class="icon-cancel" @click="unshowComment()"></span>
  <div class="rating">
   <span class="" 
    v-for="task in stars" 
    :key="task.id " 
    @click=" star() ,rate=task.rate"
    :class="' icon-star-empty'"
    >
    {{rate}}
   </span> 
   <!--<span class="icon-star-empty star" v-for="(task,index )in stars"
    :key="task.id" 
    @click=" star, rate=index+1 "
    ></span>-->
  </div> 
  <div class="show-avg"
  v-on:avg="avg"
  @click="this.$parent.avage() ,avg=avg ">
    <span>avage : {{avg}}</span>
    <span class="avg"
     ></span>
  </div>
  

  <div class="text">
    <textarea id="comment" v-model="task.nazar"
      name="comment"
     rows="1" cols="50"
     v-for="task in comments" :key="task.id"> 
    </textarea>
  
    <textarea name="nazar"
     id="comment"
      cols="4" rows="4"
       placeholder="comment..." v-model="nazar" v-bind="rate"></textarea>
  </div>
  <button type="submit" name="sabt-nazar"
   class="sabt-nazar" @click="addComment(), this.$parent.avage()"
   >ثبت نظر </button>
</div>
</template>

<script>
//import {uuid} from "vue-uuid";//
export default {
  name:"Comment",
  props: ["comments","stars",'avg','images'],
  data(){
    return{
      nazar:"",
      rate:"",

    };
  },
  methods:{
    unshowComment(){
      document.querySelector(".comment").classList.add("hide");
    },
    star: function(){
      document.querySelector(".icon-star-empty").classList.add("icon-star");
    },
    addComment: function(){
      const newComment = {
        //id:uuid.v4(),//
        nazar:this.nazar,
        rate:this.rate 
      };
      this.$emit("new-comment",newComment);
      this.nazar="";
      this.rate="";
    }  
  },
  
};
</script>

<style  scoped>
    @font-face{
        font-family: my-font;
        src:url('../assets/css/fontello.css')
    }
    .rating{
      display: inline;
    }
    .icon-star-empty{
      cursor: pointer;
      color: rgb(243, 130, 1);
      padding: 1px;
    }
    .icon-star{
      cursor: pointer;
      color: rgb(243, 130, 1);
      padding: 1px;
    }
    .icon-cancel{
      border: 2px solid rgb(255, 255, 255);
      border-radius: 5px;
      margin-top: -3px;
      margin-right:10px ;
      float: right;
      font-size: 1.3em;
      color: white;
      background-color: rgba(255, 0, 0, 0.8);
      cursor: pointer;
    }
    .icon-cancel:hover{
      background-color: rgba(255, 0, 0, 0.5) !important;
    }
    .show-avg{
      cursor: pointer;
      padding-left: 10px;
      margin-top: 10px;
      font-family:bold;
      text-align: left;
      position: relative;
      bottom: 10px;
      color: rgb(153, 82, 1);
        
    }
    .avg{
      background-color: rgb(161, 120, 66);
    }

.comment{
  margin: 10px 10%;
  padding: 10px 0px;
  background-color: rgb(251, 245, 234);
  border: rgb(170, 170, 156) solid 1px;
}
  #comment{
    border: 2px solid #ccc;
    border-radius: 4px;
    width: 100%;
  }
  
  .text{
    padding: 10px 10%;
  }
  
  .sabt-nazar{
    padding: 7px 20px;
    margin: 0px 40%;
    border-radius: 10%;
    border: rgb(167, 164, 164) 1px solid;
    background-image: none;
    font-size: 14px;
    background-color: rgb(83, 75, 75);;
    color: white;
  }
  .sabt-nazar:hover{
    background-color: rgba(75, 71, 71, 0.7);
  }

</style>
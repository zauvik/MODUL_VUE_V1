<template>
  <div class="article">
    <div class=" container text-left" style="margin-top:10px;color:gray;"><small>AppkuName > Article</small></div>
    <div class="container">
      <h2>{{title}}</h2>
      <br>
      <img :src="image" alt="url salah" class="img-fluid">
      <br>
      <div class="text-left" style="display:blcok">
          <small>article by : {{author}}</small>
        </div>
      <br>
      <br>
      <p align="left">{{content}}</p>
      <hr>
    </div>
    <Comments/>
  </div>
</template>

<script>
import Comments from "@/components/Comments.vue";
import Axios from "axios";

export default {
  name: "Article",
  components: {
    Comments
  },
  data() {
    return {
      title: "Ini Title",
      image: null,
      author: "nama author",
      content: "Ini Konten"
    };
  },
  created() {
    Axios.get("https://api.myjson.com/bins/db6io").then(response => {
      (this.title = response.data.title),
        (this.image = response.data.article_image),
        (this.author = response.data.author),
        (this.content = response.data.article_content);
    });

    /*asynchronous experiment*/
    // setTimeout(function(){
    //      console.log('1. ini dulu')
    //  },3000);

    //  console.log('2. atau ini dulu hayoo')
  }
};
</script>

<style>
.container {
  margin-top: 50px;
  margin-bottom: 30px;
}
</style>


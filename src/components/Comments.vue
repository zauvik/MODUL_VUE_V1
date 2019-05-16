<template>
  <div class="container">
    <template v-if="comments_container.length==0">
        <div class="card" style="margin:20px 0 20px 0">
            <div class="card-body">
                <h5 class="card-title text-left"><b>Nothing comment data</b></h5>
            </div>
        </div>
    </template>

    <template v-if="comments_container.length!=0">
      <div class="card" v-for="(item_comments, index) in comments_container" :key="index" style="margin:20px 0 20px 0">
        <div class="card-body">
          <h5 class="card-title text-left"><b>author : </b>{{item_comments.name}}</h5>
          <hr>
          <p class="card-text text-left"><b>Comments : </b>{{item_comments.comment}}</p>
        </div>
      </div>
    </template>
    <hr>
    <div class="input-group">
      <input
        type="text"
        v-model="form.name"
        class="form-control col-md-3"
        placeholder="enter name"
      >
      <input type="text" v-model="form.comment" class="form-control" placeholder="comment here">
      <span class="input-group-btn">
        <button
          class="btn btn-success"
          type="button"
          @click="push_comment(form.name,form.comment)"
        >Send!</button>
      </span>
    </div>
    <br>
    <br>
  </div>
</template>
<script>
export default {
  name: "Comments",
  data() {
    return {
      form: {
        name: null,
        comment: null
      },
      comments_container: []
    };
  },
  methods: {
    push_comment(data_name, data_comment) {
      var data_comment = { name: data_name, comment: data_comment }
      this.comments_container.push(data_comment)
      this.form.comment = null
      console.log(data_name + "n" + data_comment)
      console.log("comments container in state : " + this.comments_container)
    }
  },
  mounted() {
    console.log(this.comments_container);
  }
};
</script>

<template>
  <div id="showBlog">
    <h1>博客总览</h1>
    <div class="content">
      <div v-for="blog in blogs">
        <header>
          <a href="#">{{blog.title}}</a>
        </header>
        <p>{{blog.content}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "showBlog",
  data() {
    return {
      title: "",
      content: "",
      blogs: []
    };
  },
  created() {
    this.$http
      .get("https://blog-class-b959e.firebaseio.com/post.json")
      .then(function(data) {
        return data.body;
      })
      .then(function(data) {
        var Arr = [];
        for (let key in data) {
          data[key].id = key;
          console.log(data[key]);
          Arr.push(data[key]);
          // console.log(data[key].id)
        }
        this.blogs = Arr;
      });
  }
};
</script>

<style scoped>
#showBlog * {
  box-sizing: border-box;
}
#showBlog {
  background-color: rgb(102, 119, 204);
  padding: 20px;
}
#showBlog .content div {
  background-color: #ddd;
  margin-top: 20px;
  border: 1px dotted #ccc;
  padding: 20px;
}
#showBlog .content div header {
  font-size: 20px;
  font-weight: bolder;
}
#showBlog .content div header a{
    color: crimson;
}
</style>


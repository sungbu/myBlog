<template>
  <div id="addBlog">
    <h1>添加博客</h1>
    <form>
      <p>博客标题</p>
      <input type="text" v-model="blog.title" />
      <p>博客内容</p>
      <textarea v-model="blog.content"></textarea>
      <div class="checkboxs">
        <label for>Vue.js</label>
        <input value="Vue.js" id="Vue" type="checkbox" v-model="blog.categories" />
        <label for>Node.js</label>
        <input value="Node.js" id="Node" type="checkbox" v-model="blog.categories" />
        <label for>React.js</label>
        <input value="React.js" id="React" type="checkbox" v-model="blog.categories" />
        <label for>Augular4.js</label>
        <input value="Augular4.js" id="Augular4" type="checkbox" v-model="blog.categories" />
      </div>
      <p>作者</p>
      <select v-model="blog.author">
        <option v-for="author in authors">{{author}}</option>
      </select>
    </form>
    <hr />
    <div class="des">
      <h4>博客总览</h4>
      <p>博客标题：{{blog.title}}</p>
      <p>博客内容：</p>
      <p>{{blog.content}}</p>
      <p>博客分类：</p>
      <ul>
        <li v-for="categorie in blog.categories">{{categorie}}</li>
      </ul>
      <p>作者：{{blog.author}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "addBlog",
  data() {
    return {
      blog: {
        categories: [],
        title: "",
        content: "",
        author: "Prince"
      },
      authors: ["Prince", "Henry", "Peter"]
    };
  }
};
</script>

<style scoped>
#addBlog * {
  box-sizing: border-box;
}
#addBlog {
  margin: 20px auto;
  max-width: 600px;
  padding: 20px;
}
#addBlog input[type="text"],
textarea,
select {
  width: 100%;
  height: 35px;
}
#addBlog textarea {
  height: 120px;
}
#addBlog .checkboxs {
  text-align: center;
}
#addBlog .checkboxs label {
  padding-left: 10px;
}
#addBlog .des{
    border:1px dotted #ccc;
    padding:10px;
}
</style>



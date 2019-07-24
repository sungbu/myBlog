<template>
  <div id="app">
    <showBlog/>
    <!-- <addBlog/> -->
  </div>
</template>

<script>
import addBlog from './components/AddBlog'
import showBlog from './components/ShowBlogs'

export default {
  name: 'App',
  components: {
    addBlog,
    showBlog
  }
}
</script>

<style>
</style>

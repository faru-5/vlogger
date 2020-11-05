<template>
  <div>
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
import addBlog from './components/addBlog'
import Header from './components/Header'

export default {
  components:{
    'add-blog':addBlog,
    'appHeader':Header
  }

}
</script>

<style>

</style>
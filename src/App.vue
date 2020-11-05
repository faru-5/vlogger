<template>
  <div>
    <router-view></router-view>
  </div>
</template>

<script>
import addBlog from './components/addBlog'

export default {
  components:{
    'add-blog':addBlog
  }

}
</script>

<style>

</style>
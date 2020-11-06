<template>
  <div>
    <app-header></app-header>
    <router-view :posts="posts"></router-view>
    <app-footer></app-footer>
  </div>
</template>

<script>
import feed from './components/feed'
import Header from './components/Header'
import Footer from './components/Footer'

export default {
  components:{
    'add-feed':feed,
    'appHeader':Header,
    'appFooter':Footer
  },
  data: function(){
    return {
      posts:[]
    }
  }

}
</script>

<style>

</style>
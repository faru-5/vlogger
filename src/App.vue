<template>
  <div>
    <app-header></app-header>
    <router-view :posts="posts"></router-view>
  </div>
</template>

<script>
import feed from './components/feed'
import Header from './components/Header'

export default {
  components:{
    'add-feed':feed,
    'appHeader':Header
  },
  data: function(){
    return {
      posts:[
        {
          title:"Today Was Good", 
          content:"Lorem ipsum dolor sit amet consectetur, adipisicing elit. Explicabo quidem cupiditate ipsam! Magni quas atque temporibus sapiente consequatur dolor, eveniet quidem impedit in velit ad est, quam nam odit tempore." 
        },
        {
          title:"Today Was Good", 
          content:"Lorem ipsum dolor sit amet consectetur, adipisicing elit. Explicabo quidem cupiditate ipsam! Magni quas atque temporibus sapiente consequatur dolor, eveniet quidem impedit in velit ad est, quam nam odit tempore." 
        },
        {
          title:"Today Was Good", 
          content:"Lorem ipsum dolor sit amet consectetur, adipisicing elit. Explicabo quidem cupiditate ipsam! Magni quas atque temporibus sapiente consequatur dolor, eveniet quidem impedit in velit ad est, quam nam odit tempore." 
        }
      ]
    }
  }

}
</script>

<style>

</style>
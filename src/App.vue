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
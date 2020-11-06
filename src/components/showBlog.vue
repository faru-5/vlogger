<template>
  <div> 
      <div class="row mb-2">
            <div class="col-md-6" v-for="post in posts.reverse()" :key="post.id">
                <div class="post row no-gutters shadow-lg border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
                    <div class="post col p-4 d-flex flex-column position-static">

                        <!-- TAG -->

                        <!-- <strong class="d-inline-block mb-2 text-white bg-primary">World</strong> -->

                        <h3 class="mb-0">{{ post.title }} </h3>
                        <span class="mb-1 mL-auto text-transparent">Nov 12</span>
                        <div class="card-text mb-auto" :style="{'max-height':'80px'}" :inner-html.prop="post.content"></div>
                    </div>
                    <div class="shad">
                                
                    </div>
                </div>
                <div class="">
                    <button class="btn btn-primary">View Post</button>
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['posts'],
    data(){
        return {
            seeMorePost:false,
            postContentHeight:"20px"
        }
    },
    created(){
            for (this.post of this.posts){
                if(this.post.content.length > 20){
                    this.seeMorePost = true
                } else{
                    this.seeMorePost = false
                }
            }
    }
}
</script>

<style>
    .shad{
        position: absolute;
        left: 0;
        bottom: -45px;
        width: 100%;
        height: 80px;
        background:  linear-gradient(to bottom, transparent, rgba(117, 19, 93, 0.73));
 
    }
    .post{
        /*  */
    }
</style>
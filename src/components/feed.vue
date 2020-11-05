<template>
    <div class="container">
        <button v-if="!postArea" @click="postArea = true" class="w-100 p-2 mb-2 btn btn-warning">Post What's Happening Now </button>
        <form v-else class="form-group">
            <textarea class="form-control mb-3" v-model="title" rows="1" id="my_editor" placeholder="title"></textarea>
            <textarea class="form-control" v-model="content" rows="5" id="my_editor" placeholder="what is on your mind?"></textarea>
            <p class="lead">{{content}}</p>
            <button @click.prevent = "post" class="btn btn-info m-2">POST</button>
        </form>

        <showBlog :posts = "posts"></showBlog>

    </div>
</template>


    
<script>

    import showBlog from './showBlog'
    
    export default {
        components:{
            showBlog:showBlog
        },
        props:[ 'posts'],
        data(){
            return {
                title:'',
                content:'',
                postArea:false
            }
        },
        methods:{
            post(){
                this.posts.push(
                    {
                        title:this.title,
                        content:this.content
                    }
                )
                this.title = '',
                this.content = '',
                this.postArea = false
            }
        }
    }
    
</script>

<style>

</style>
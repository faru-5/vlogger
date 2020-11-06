<template>
    <div class="container">
        <button v-if="!postArea" @click="postArea = true" class="w-100 p-2 mb-2 btn btn-warning">Post What's Happening Now </button>
        <form v-else class="form-group">
            <textarea class="form-control mb-3" v-model="title" rows="1" id="my_editor" placeholder="title"></textarea>
            <textarea v-if="!advancedTextArea" class="form-control" v-model="content" rows="5" id="my_editor" placeholder="what is on your mind?"></textarea>
            <!-- <p class="lead">{{content}}</p> -->
            <div v-else id="app">
                <ckeditor v-model="content" ></ckeditor>
            </div>
            <button class="btn btn-outline-primary" @click.prevent="advancedTextArea = !advancedTextArea">Change Typing Mode</button>
            <button @click.prevent = "post" class="btn btn-info m-2">POST</button>
        </form>

        
        <div v-if="!dataLoaded" class="text-center">
            <div class="spinner-border" role="status">
                <span class="sr-only">Loading...</span>
            </div>
        </div>
        
        <showBlog v-else :posts = "posts"></showBlog>

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
                postArea:false,
                dataLoaded:false,
                advancedTextArea:false
            }
        },
        methods:{
            post(){
                this.posts.push(
                    {
                        title:this.title,
                        content:this.content
                    }
                );

                this.$http.post('https://vlogger-e691b.firebaseio.com/data.json', this.posts)
                .then(response => {
                    console.log(response)
                }, error =>{
                    console.log(error)
                })
                this.title = '',
                this.content = '',
                this.postArea = false
            }
        },
        created(){
            this.$http.get('https://vlogger-e691b.firebaseio.com/data.json')
                .then(response => {
                    return response.json()
                }) .then(data => {
                    const fetchedData = [];
                    for(let key in data){
                        fetchedData.push(data[key])
                    }
                    this.posts = fetchedData;
                    this.dataLoaded = true;
                })
        }
    }
    
</script>

<style>

</style>
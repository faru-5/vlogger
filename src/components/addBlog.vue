<template>
  <div>
    <div v-if="submitted">
        <h3>Thanks For posting</h3>
    </div>
    <form v-else>
        <h2>add blog</h2>
        <select v-model="blog.author">
            <option>Select Author</option>
            <option v-for="author in authors" >{{author}}</option>
        </select>
        <label for="">Blog Title</label>
        <input id="blogTitle" type="text" v-model.lazy="blog.title" name="" >
        <label for="">Blog Content</label>
        <textarea v-model="blog.content" ></textarea>
        <div id="checkboxes">
            <label id="label">Technology</label>
            <input type="checkbox" id="check" value="Technology" v-model="blog.categories">
            <label id="label">Business</label>
            <input type="checkbox" id="check" value="Business" v-model="blog.categories">
            <label id="label" >Sport</label>
            <input type="checkbox" id="check" value="Sport" v-model="blog.categories"><br>
            <input type="text" ref="tag" v-model="tag_adder" @keyup.,="addTag" >
        </div>
        
        <button @click.prevent="post">Post</button>
    </form>
    <div id="preview">
        <h4>preview blog</h4>
        <p>Author: {{blog.author}}</p>
        <h5>Blog TItle: </h5>
        <p>{{blog.title}}</p>
        <h5>blog Content: </h5>
        <p>{{blog.content}}</p> 
        <p>
            <span v-for="category in blog.categories" :key="category.id" id="tag"> 
                <span @click="blog.categories.pop(category)" id="x">X</span> 
                {{category.toString()}}
            </span> 
        </p>
        
    </div>
  </div>
</template>

<script>
export default {
    data(){
       return {
            blog:{
                title:'',
                content:'',
                categories:[],
                author:''
            },
            authors:['Faruq Ismael', 'Mayko Solomon', 'Natinael Bayisa'],
            tag_adder:'',
            submitted:false
       }
    },
    methods:{
        addTag(){
            this.blog.categories[this.blog.categories.length] = this.$refs.tag.value.split(',').slice(0,this.blog.categories.length-1)
            console.log(this.blog.categories)
            this.tag_adder=''
        },
        post(){
            this.$http.post('https://jsonplaceholder.typicode.com/posts',{
                title:this.blog.title,
                body:this.blog.content,
                userId:1
            }).then(function(data){
                console.log(data);
                this.submitted = true
            });
        }
    }
}
</script>

<style>
    body{
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        margin: 5%;
    }
    #blogTitle, textarea{
        background: none;
        border: none;
        width: 400px;
        height: 40px;
        border: 1px solid black;
    }
    label{
        display: block;
        margin: 15px 0 10px ;
    }
    #preview{
        position: absolute;
        right: 10px;
        top: 20px;
        text-align: center;
        width: 500px;
    }
    #tag{
        border-radius: 20px;
        padding: 5px;
        background: chartreuse;
        margin-right: 10px;
    }
    #x{
        background: gray;
        padding: 5px;
        border-radius: 50%;
        cursor: pointer;
    }
    #check{
        display: inline-block;
    }
    #label{
        display: inline-block;
    }
</style>
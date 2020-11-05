<template>
  <div> 
      <div class="row mb-2">
            <div class="col-md-6" v-for="post in posts.reverse()" :key="post.id">
                <div class="row no-gutters shadow-lg border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
                    <div style="font-family:Verdana;" class="col p-4 d-flex flex-column position-static">
                        <strong class="d-inline-block mb-2 text-white bg-primary">World</strong>
                        <h3 class="mb-0">{{ post.title }} </h3>
                        <div class="mb-1 mr-auto w-25 bg-warning text-transparent">Nov 12</div>
                        <p class="card-text mb-auto">{{ post.content }}</p>
                        <a href="#" class="stretched-link">Continue reading</a>
                    </div>
                    <div class="col-auto d-lg-block">
                        <img src="./25567.jpg" class="w-100" alt="">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['posts']
}
</script>

<style>

</style>
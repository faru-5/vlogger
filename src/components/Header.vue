<template>
  <div class="p-5"> <!-- CONTROLING THE PADDING OF THE PAGE BELOW THE HEADER-->
      <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-dark">
        <a class="navbar-brand bg-danger p-2" href="">VLOGGER</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarCollapse" aria-controls="navbarCollapse" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item active">
                    <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
                </li>
            </ul>

            <form class="form-inline mt-2 mt-md-0">
                <input class="form-control mr-sm-2" type="text" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
            </form>
            
            <ul class="navbar-nav mr-3 ml-2">
                <li class="nav-item active">
                    <a class="nav-link btn btn-outline-warning my-2 my-sm-0 mr-2" href="#">SIGN IN</a>
                </li>
                <li class="nav-item active">
                    <a class="nav-link btn btn-outline-warning my-2 my-sm-0" href="#">LOGIN</a>
                </li>
            </ul>
        </div>
    </nav>
  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>
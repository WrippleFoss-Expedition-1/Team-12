<template>
    <nav class="navbar navbar-expand-md">
        <div class="container-fluid">
            <div class="navbar-header animated bounceInRight" >
                <a class="navbar-brand" href="/">{{ brand }}</a>
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
            </div>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="nav navbar-nav animated fadeInDown ml-auto">
                   <li v-for="(NameRoute,index) in NameRoutes" :key="index" class="w-auto mx-5">
                       <router-link  class="shubham" :to="{ name : NameRoute }">{{ Names[index]}}
                       </router-link>
                   </li>
                </ul>
            </div>
            <!-- /navbar-collapse -->
        </div>
        <!-- /container-fluid -->
    </nav>
</template>
<script>
export default {
  data() {
    return {
      brand: 'NAME', //prefer to put name in caps
      NameRoutes: ["portfolio", "freebies", "about", "contact"],
      Names: ["My Work", "FreeBies", "About Me", "Contact"]
    };
  },
  methods:{
      ZoomInAnimation: function(){
        console.log('animated')
      }
  }
};
</script>

<style scoped>
.shubham{
 letter-spacing: 2px;

}
.shubham:hover{
 color: teal;
 transform: scale(1.1);
 /* transform not working */
}
</style>

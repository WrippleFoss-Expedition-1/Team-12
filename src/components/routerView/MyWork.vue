<template>
   <section id="wrapping">
    <div class="py-3" v-for="(sample,index) in workSamples" :key="index" :class="{ backgroundColor: index%2 === 0}">
        <div class="container">
            <div class="row mt-5">
            <div class="col-md-6 animated" :class=" {'order-2': index%2, 'fadeInLeft':index%2, 'fadeInRight':index%2===0, 'text-right':index%2===0 }">
                <div class="row" style="margin-top:25%">
                    <div class="col">
                        <h4> PROJECT {{index}} </h4>
                        <p> <u> DESCRIPTION:</u> <span>{{ sample.description }}</span></p>
                        <a :href=sample.github_link target="_blank" class="btn btn-block btn-primary" 
                        style="color:white">
                          <span>See on </span>
                          <i class="fab fa-github"></i>
                        </a>
                    </div>
                </div>
            </div>
            <div class="col-md-6 d-none d-md-block animated" :class="{'fadeInLeft':index%2, 'fadeInRight':index%2===0 }">
                <div class="card">
                    <div class="card-img" style="width: 50% !important">
                        <img :src="sample.img" :alt="index" style="width:200%; max-height:400px">
                    </div>
                </div>
            </div>
        </div>
        </div>
        
    </div>
</section>
</template>

<script>
export default {
  data: function() {
    return {
      workSamples: {
        1: {
          description: "Sint aliquip officia aute qui non cillum.",
          img:
            "https://images.unsplash.com/photo-1485856407642-7f9ba0268b51?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=9c2bca0bb61f47e9da0fa59ec698c981&auto=format&fit=crop&w=750&q=80",
          github_link: ""
        },
        2: {
          description:
            "Incididunt deserunt Lorem sunt consectetur ad eiusmod veniam id consequat fugiat sit.",
          img:
            "https://images.unsplash.com/photo-1506526794364-ba711a0d97fc?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=58b59efbf7d9aa9dc6cce27b23e0c563&auto=format&fit=crop&w=334&q=80",
          github_link: ""
        }
      }
    };
  }
};
</script>

<style scoped>
.backgroundColor{
    background: black;
    color: white
}
</style>

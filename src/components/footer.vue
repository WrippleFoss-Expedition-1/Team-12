<template>
    <div style="background: black" class="text-primary">
        <footer class="container" style="bottom: 0;position: relative">
            <div class="row pt-3">
                <div class="col-md-4">
                    <!-- put somwthing  -->
                </div>
                <div class="col-md-4">
                    <div class="flip">
                        <router-link :to="{ name: 'contact' }">
                            hire me
                        </router-link>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="flip">Follow Me</div>
                    <br>
                    <ul>
                        <li v-for="(classIcon,index) in classFontAwesomeIcon" :key="index">
                            <a :href="link[index]">
                                <i :class="classIcon">
                                </i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
export default {
  data() {
    return {
      classFontAwesomeIcon: ["fab fa-facebook-f", "fab fa-linkedin-in"],
    link : ['https://www.facebook.com/shubham.kakkar1998', 'https://www.linkedin.com/in/shubham-kakkar-5b53b2158/']
    };
  }
};
</script>

<style scoped>
ul {
  padding: 0;
  display: -webkit-box;
  list-style: none;
}

li {
  margin-right: 25px;
}

i{
    font-size: 20px;
}

i:hover{
    font-size: 25px;
}

.flip{
    transform :scale(1,-1); 
    text-transform : uppercase; 
    letter-spacing : 3px
}

.flip:hover{
    transform: scale(1,1)
}

.flip:nth-child(1){
    cursor: pointer;
}
</style>

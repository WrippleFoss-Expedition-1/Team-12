<template>
<div id="wrapper" style="overflow:hidden">
    <section id="part-1" style="background : black;" class="animated fadeIn">
        <!-- background img + word art -->
        <div class="row justify-content-center animated bounceIn" id="animationAdd_on_hover" @mouseover="addTada" @mouseout="removeTada" style="padding : 2%">
            <h1 style="margin:auto; letter-spacing : 10px; color:white" class="display-3 col-sm-6 text-center">
                {{homeQuotation}}
            </h1>
            <!-- adjust the grid system as per your quote -->
        </div>
        <div class="row" style="margin-top:-50px">
            <div class="col-sm-8" style="margin:auto; margin-top:0;">
                <div class="parallax">
                    <img src="../../assets/images/home.png" alt="home" class="img-fluid" style="height:100%">
                </div>
            </div>
        </div>

    </section>

    <section id="part-2" style="margin-top:50px">
        <div class="container">
            <div class="row">
                <h3 class="col-sm-8 display-4 text-primary">
                    <p> Hey, my name is <span style="color:black">{{ name }}</span>,</p>I am a
                    <vue-typer :text=profile></vue-typer>
                </h3>
                <!-- Would highly recommend changing the grid system as per the name and  profile -->
                <div class="col-sm-4">
                    <!-- border-radius : 50%; -->
                    <img src="" alt="avatar">
                </div>
            </div>
            <div class="row">
                <div class="col-sm-8 offset-sm-4 text-right animated fadeInRightBig" id="demo">
                    <!-- animated oneliner -->
                    <h5>I believe : </h5>
                    <span>{{oneliner}}</span>
                    <!-- SUGGESTION REQUIRED -->
                </div>
            </div>
        </div>
    </section>
    <!-- cards with work-preview'card link attached to it, highighted when clicked -->
    <section id="part-3" style="background : black">
        <div>
            <div class="row mb-3">
                <div class="col text-center p-0 text-primary">
                    <h3 class="display-1"> Skill Set </h3>
                </div>
            </div>
            <div class="row">
                <div class="col" style="color:white">
                    <div class="row">
                        <div class="col-sm-4 my-4" 
                        data-toggle="tooltip" data-placement="top" title="Click" v-for="(skill, index) in skillsCard.skills"
                         :key="index">
                      <div class="card cardHover border-0" style="background: 0">
                        <div class="card-body text-center" @mouseover="hoverAnimate(index)" @mouseout="removeHover(index)">
                            <h4 class="card-tittle">
                                {{ skill }}
                                <!-- if you want to add more skills add them in the data(){ .. } inside the card-data obj -->
                            </h4>
                            <div class="row">
                                <!-- animated cards with hover effect -->
                                <div class="col-md-8 offset-md-2">
                                    <div class="card-text">
                                        <p class="exp"> # {{ skillsCard.experianceYear[index] }} of year of work</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                       </div>
                    </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section id="part-4">
        <div class="row">
            <h3 class="col-sm-10 offset-sm-1 text-center" style="letter-spacing:2px">
                Work Preview
            </h3>
        </div>
        <div class="row my-5">
            <div class="col-sm-3 py-5" v-for="(workTitle,index) in workPrevious.title" :key="index">
                <div class="card text-center border-0 hoverEffect transitionAnimated" :class="{zigzag: index%2}">
                    <div class="card-img">
                        <img :src="workPrevious.prevImage[index]" :alt="index">
                    </div>
                    <div class="card-body">
                        <div class="card-title my-3">
                            <h3>
                                {{ workTitle }}
                            </h3>
                            </div>
                        <div class="card-subtitle">
                            {{ workPrevious.descrition[index] }}
                        </div>
                        <div class="card-text my-3">
                            <a :href=workPrevious.githubLink[index] class="btn btn-block btn-primary" style="color: white">
                                See on
                                <i class="fab fa-github"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</div>
</template>

<script>
import { VueTyper } from "vue-typer";
export default {
  data() {
    return {
      homeQuotation: "Built My Way",
      name: "Shubham Kakkar",
      profile: "Front-End Developer",
      oneliner: "Its never too early to start and never too late to end.",

      skillsCard: {
        skills: [
          "HTML",
          "CSS",
          "Vanilla JS",
          "jQuery",
          "AJAX",
          "Bootstrap-3/4",
          "Vue.js(Vuex & Vue-router)",
          "Vue-Resource & Axios"
        ],
        experianceYear: [2, 2, 2, 2, 2, 2, 1.5, 1, 1]
      },

      conditionBool_profile: false,
      star: false,
      // star is responsible to add ** to vue's card and boostrap's at top-right  -> my best

      workPrevious: {
        prevImage: [],
        title: ["Project 1", "Project 2", "Project 3", "Project 4"],
        descrition: [
          "Description 1",
          "Description 2",
          "Description 3",
          "Description 4"
        ],
        githubLink: []
      }
    };
  },
  components: {
    VueTyper
  },
  methods: {
    hoverAnimate: function() {
      $(".cardHover").addClass("shadow");
      // alert($('.cardHover').attr('class'))
    },
    removeHover: function() {
      $(".cardHover").removeClass("shadow");
      $(".cardHover").addClass("transitionAnimated");
    },
    addTada: function() {
        var temp = document.getElementById("animationAdd_on_hover");
      temp.classList.remove("bounceIn");  
      temp.classList.add("tada");
    },
    removeTada: function() {
      document.getElementById("animationAdd_on_hover").classList.remove("tada");
    }
  },
  mounted() {
    // this.hoverCard(0),
    (this.star = true),
      //use the sticky button of hiration for controlling the conditionBool_profile
      $('[data-toggle="tooltip"]').tooltip();
  },
  computed: {}
};
</script>

<style scoped>
.my-4{
    margin: 0 !important;
    padding: 0 !important;
}
section {
  margin-bottom: 5%;
  padding: 5%;
}
.parallax {
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.cardHover {
  border-radius: 10%;
  height: 110px;
  width: auto;
}

.cardHover:hover {
  transform: scale(1.1);
  color:royalblue !important
}

.transitionAnimated {
  transition-duration: 1s;
}


.zigzag{
    margin-top: -20%;
}

.hoverEffect:hover{
    box-shadow: 1.2px 1.2px 2px 2px grey;
}


</style>


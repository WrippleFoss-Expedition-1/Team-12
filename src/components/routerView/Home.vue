<template>
<div id="wrapper" style="overflow:hidden">
    <section id="part-1" style="background : #F7F4FA;">
        <!-- background img + word art -->
        <div class="row">
                <h1 v-for="(homeQuote, index) in homeQuotation" :key="index" class="display-3 col-sm-4 text-center" style="color:#662896">
                    {{homeQuote}}
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
                <h3 class="col-sm-10 offset-sm-1 ml-auto" style="font-weight:normal;word-break:break-all">
                    My Name is
                    <vue-typer :text=name>
                    </vue-typer>
                    , I am a
                    <vue-typer :text=profile></vue-typer>
                </h3>
                <!-- Would highly recommend changing the grid system as per the name and  profile -->
            </div>
            <div class="row">
                <div class="col-sm-10 offset-sm-1 text-center" id="demo">
                    <!-- animated oneliner -->
                    <span>{{oneliner}}</span>
                    <!-- SUGGESTION REQUIRED -->
                </div>
            </div>
        </div>
    </section>
    
    <!-- cards without work-preview'card links attatched to it -->
    <!-- <section id="part-3"  style="background:linear-gradient(110deg, #632998, #5B4CB3)">
         skills slideShow with progressbar(animated)
        <div class="container">
            <div class="row mb-3">
                <h3 style="text-transform:uppercase; margin:auto;color:#F3B442">SkillSet</h3>
                <div class="row">
                  <div class="col-md-3 col-sm-6 ml-auto my-4" v-for="(skill, index) in skillsCard.skills" :key="index">
                    <div class="card cardHover" @mouseover="hoverAnimate(index)" @mouseout="removeHover(index)">
                        <div class="card-body text-center">
                            <h4 class="card-tittle">
                                {{ skill }}
        //if you want to add more skills add them in the data(){ .. } inside the card-data obj
                            </h4>
                            <div class="row">
                                //animated cards with hover effect
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
      </section>-->
  
    
    <!-- cards with work-preview'card link attached to it, highighted when clicked -->
    <section id="part-3" class="bg-light">
        <div class="container">
            <div class="row">
                <h3 style="text-transform:uppercase; margin:auto;margin-bottom:5% !important;color:#F3B442;	background: linear-gradient(to right, #30CFD0 0%, #330867 100%);-webkit-background-clip: text;-webkit-text-fill-color: transparent;">SkillSet</h3>
                <div class="row">
                    <div class="col-md-3 col-sm-6 ml-auto my-4" data-toggle="tooltip" data-placement="top" title="Click" v-for="(skill, index) in skillsCard.skills"
                        :key="index">
                        <div class="card cardHover border-0" style="background: 0 !important; border-right: 2px solid black !important; border-bottom: 2px solid black !important">
                            <div class="card-body text-center" style="padding-top:20%" @mouseover="hoverAnimate(index)" @mouseout="removeHover(index)">
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
    </section>
    <section id="part-4">
        <div class="container">
            <div class="row">
                <h3 class="col-sm-10 offset-sm-1 text-center" style="letter-spacing:2px">
                    Work Preview
                </h3>
            </div>
            <div class="row my-5">
                <div class="col-sm-3" v-for="(workTitle,index) in workPrevious.title" :key="index">
                    <div class="card text-center my-4" @mouseover="TypeWriterEffectON" @mouseout="TypeWriterEffectOFF">
                        <div class="card-img">
                            <img :src="workPrevious.prevImage[index]" :alt="index">
                        </div>
                        <div class="card-body">
                            <div class="card-title my-3">
                                <h3 v-if="By_default">
                                    {{ workTitle }}
                                </h3>
                                <h3 v-if="hover">
                                    <vue-typer :text=workTitle></vue-typer>
                                </h3>
                            </div>
                            <div class="card-subtitle">
                                {{ workPrevious.descrition[index] }}
                            </div>
                            <div class="card-text my-3">
                                <a :href=workPrevious.githubLink[index] class="btn btn-block btn-primary" style="color:white">
                                    See on
                                    <i class="fab fa-github"></i>
                                </a>
                            </div>
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
      homeQuotation: ["Built", "My", "Way"],
      name: "First-Name Last-Name",
      profile: "Front-End Developer",
      oneliner: "/* Describe Your self */",

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
      },

      By_default: true,
      hover: false
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
    TypeWriterEffectON: function() {
      this.By_default = false;
      this.hover = true;
    },
    TypeWriterEffectOFF: function() {
      this.By_default = true;
      this.hover = false;
    }
  },
  mounted() {
    (this.star = true),
      //use the sticky button of hiration for controlling the conditionBool_profile
      $('[data-toggle="tooltip"]').tooltip();
  }
};
</script>

<style scoped>
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
  color: cornflowerblue;
  border-radius: 10%;
  height: 170px;
  width: auto;
  box-shadow: 1.25px 1.25px 1.25px 1.25px black;
}

.cardHover:hover {
  transform: scale(1.1);
}

.cardHover:nth-of-type(even) {
  height: 200px;
  /* 
    * not working
    * adjust margin accordingly 
 */
}

.shadow {
  box-shadow: 2.5px 2.5px 2.5px 2.5px white;
  transition-duration: 0.3s;
}
.transitionAnimated {
  transition-duration: 1s;
}

/***********
  TOOLTIP
************/
.tootltip-inner,
.tootltip-arrow {
  background: linear-gradient(66deg, blue, blueviolet) !important;
  /* not working */
}
</style>


<template>
<section id="wrapping">
    <div class="container text-primary mt-5" style="">
        <div class="row py-3">
            <div class="col-md-6 d-none d-md-block target-img transitionAnimated animated fadeInUpBig" id="grayscaleRemove">
                <!-- img -->
                <h4 class="row target-img-text">
                    <p style="width: 100%">Let's</p>
                    <p  style="width: 100%">Work</p>
                    <p  style="width: 100%">Together</p>
                </h4>
            </div>
            <div class="col-md-6 col-sm-12 animated fadeInDownBig">
                <form class="form" role="form" autocomplete="off">
                    <div class="form-group row" v-for="(label, index) in label_array" :key="index">
                        <label class="col-lg-3 col-form-label form-control-label">{{ label }} :</label>
                        <div class="col-lg-9">
                            <input @focus="grayscaleRemove" class="form-control" :type="input_type_array[index]" :placeholder="placeholder_text_array[index]" required>
                        </div>
                    </div>
                    <div class="form-group row">
                        <label class="col-lg-3 col-form-label form-control-label">Work Requirement :</label>
                        <div class="col-lg-9">
                            <textarea name="Work Requirement - description" id="" cols="52" rows="5"></textarea>
                        </div>
                    </div>
                    <div class="form-group row">
                        <label class="col-lg-3 col-form-label form-control-label"></label>
                        <div class="col-lg-9">
                            <input type="button" class="btn btn-block btn-primary" value="Save Changes" style="color:white">
                            <input type="reset" class="btn btn-block btn-secondary" value="Cancel">
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</section>
</template>

<script>
export default {
  data: function() {
    return {
      label_array: ["First Name", "Last Name", "Email", "Company", "Website"],
      input_type_array: ["text", "text", "email", , "text", "url"],
      placeholder_text_array: ["Jane", "Paul", "example@mail.com", "", ""]
    };
  },
  methods: {
    grayscaleRemove() {
      document
        .getElementById("grayscaleRemove")
        .classList.add("dynammicGrayscale_Remove");
    }
  }
};
</script>

<style scoped>
.target-img {
  background: url("https://images.unsplash.com/photo-1518600506278-4e8ef466b810?ixlib=rb-0.3.5&ixid=eyJhcHBfaWQiOjEyMDd9&s=858391bd28bf4aadaa5b3e0750edb485&auto=format&fit=crop&w=693&q=80");
  filter: grayscale(100%);
}
.dynammicGrayscale_Remove,
.target-img:hover {
  filter: grayscale(0);
}

.target-img-text {
  font-size: 50px;
  width: 100%;
  color: black;
}
.transitionAnimated{
  transition-duration: 0.5s;
}
</style>

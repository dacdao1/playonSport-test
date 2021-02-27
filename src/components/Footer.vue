<template>
  <!-- Footer -->
      <footer class="page-footer font-small mdb-color pt-4 entirePage">

        <!-- Footer Links -->
        <div class="container text-center text-md-left">

          <!-- Footer links -->
          <div class="row text-center text-md-left mt-3 pb-3">

            <!-- Grid column -->
            <div class="col-md-3 col-lg-3 col-xl-3 mx-auto mt-3">
              <img src="../assets/playonLogo2.svg"/>
            </div>
            <!-- Grid column -->

            <hr class="w-100 clearfix d-md-none">

            <!-- Grid column -->
            <div class="col-md-2 col-lg-2 col-xl-2 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold" style="color: white">THE NFHS NETWORK</h6>
              <p>
                <a href="#!">About NFHS Network</a>
              </p>
              <p>
                <a href="#!">Help & Customer Support
  </a>
              </p>
              <p>
                <a href="#!">NFHS.org</a>
              </p>
              <p>
                <a href="#!">PlayOn! Sports</a>
              </p>
              <p>
                <a href="#!">High School Support Program</a>
              </p>
            </div>
            <!-- Grid column -->

            <hr class="w-100 clearfix d-md-none">

            <!-- Grid column -->
            <div class="col-md-3 col-lg-2 col-xl-2 mx-auto mt-3">
              <h6 class="text-uppercase mb-4 font-weight-bold" style="color: white">BROWSE OUR CONTENT</h6>
              <p>
                <a href="#!" target="_blank">Ways to Watch</a>
              </p>
              <p>
                <a href="#!" target="_blank">Find Your School</a>
              </p>
              <p>
                <a href="#!" target="_blank">The NFHS Network Store - DVD/DTos</a>
              </p>

            </div>



        </div>
          <!-- Footer links -->

          <hr>

          <!-- Grid row -->
          <div class=" text-center">

            <!-- Grid column -->
            <div>

              <!--Copyright-->
              <p style="color:white;  ">© 2020 NFHS Network LLC | NFHS Network is part of the CBS Sports Digital Network. | Version: 11340</p>


            </div>
            <!-- Grid column -->



          </div>
          <!-- Grid row -->

        </div>
        <!-- Footer Links -->

      </footer>
      <!-- Footer -->

</template>

<script>
export default {
  name: 'Footer',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.entirePage{

}
footer {
  background-color:#001B34;
  padding: 20px 0;
}

.footer-links {
  line-height: 48px;
}

.footer-links li {
  float: left;
}

.footer-links li a {
  color: #fff;
  margin-right: 15px;
  transition: all 0.3s ease-in-out;
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
}

.footer-links li a:hover {
  color: #0AA8ED;
}

.copyright {
  margin-top: 10px;
  float: right;
}

.copyright p {
  color: #fff;
}

.copyright p a {
  color: #fff;
}

.copyright p a:hover {
  color: #0AA8ED;
}
</style>

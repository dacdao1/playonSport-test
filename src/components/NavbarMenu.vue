<template>

    <div class="entirePage">


      <div>
  <b-navbar toggleable="lg" type="dark">
    <b-navbar-brand href="#">  <img src="../assets/playonLogo.svg" alt="nfhs logo" style="width:40px; margin-right: -1px"></b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Watch Events</b-nav-item>
        <b-nav-item href="#">Browse</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="mr-auto">
        <b-nav-form>
          <b-form-input  placeholder="Search" style="width: 440px; background: transparent; margin-left: 15px; margin-right: 20px "></b-form-input>

            <b-button variant="outline-light">Subscribe Now</b-button>
        </b-nav-form>

        <b-navbar-nav>
          <b-nav-item href="#">Log In</b-nav-item>

        </b-navbar-nav>


      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
    </div>

</template>

<script>
export default {
  name: 'NavBarMenu',
  props: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.entirePage{
background: #05243F;
font-family:Montserrat,sans-serif;
color: white;
font-size: 20px;

}
</style>

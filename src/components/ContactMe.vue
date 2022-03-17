<template>
  <div class="container-sm card bg-light text-left mt-4 col-lg-6 col-md-9 col-11">
    <p class="mt-2 mx-auto"><strong>Feel free to contact me for more information!</strong></p>
    <div class=" col-sm-8 col-lg-6 col-10 mx-auto">
      
      <!-- education -->
      <div class="mt-2 mb-3">
        <span class="lead">University of Waterloo</span><br>
        Mathematics Honours (co-op) <br>
      </div>

      <!-- contact info -->
      <div class="d-flex flex-column justify-content-center">
        <div>
          <button class="btn"><span><font-awesome-icon icon="phone" /></span></button>
          <span class="align-self-center">+1 (905)-616-8745</span>
        </div>
        <div>
          <a class="btn btn-light btn-social mr-1"  href="mailto:michaelxkayo@hotmail.com">
            <span><font-awesome-icon icon="envelope" /></span>  
          </a> 
          <span class="align-self-center">michaelxkayo@hotmail.com</span>
        </div>
        <div>
          <button class="btn"><span><font-awesome-icon icon="map-marker" /></span></button>
          <span class="align-self-center">570 Maplehurst Ave. Oakville ON</span>
        </div>        
      </div>

      <!-- Links -->
      <div class="row justify-content-center mt-4 mb-3">
        <a class="btn btn-outline-secondary mr-3 btn-circle btn-lg d-flex justify-content-center" href="https://github.com/kayoMichael" target="_blank">
            <span class="align-self-center"><font-awesome-icon :icon="['fab', 'github']" size="6x" class="icon-button"/></span>
        </a>
        <a class="btn btn-outline-secondary mr-3 btn-lg d-flex justify-content-center btn-sq" href="https://www.linkedin.com/in/michael-li-72115222b/" target="_blank">
          <span class="align-self-center"><font-awesome-icon :icon="['fab', 'linkedin']" size="6x" class="icon-button" /></span>
        </a>
        <a class="btn btn-outline-secondary btn-circle btn-lg d-flex justify-content-center" href="https://www.facebook.com/li.michael.7509836/" target="_blank">
          <span class="align-self-center"><font-awesome-icon :icon="['fab', 'facebook']" size="6x" class="icon-button" /></span>
        </a>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'ContactMe',
  props: {
    msg: String
  }
}
</script>

<style scoped>

  .btn-circle {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }

  .btn-sq {
    width: 40px;
    height: 40px;
  }

  .icon-button {
    width: 39px;
    height: 43px;
  }

</style>
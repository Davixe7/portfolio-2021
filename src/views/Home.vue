<template>
  <div class="home">
    <div class="row">
      <div class="col-lg-6">
        <h1>Desarrollo de Software a Medida</h1>
        <div class="caption">
          Convierte tu idea de negocio en un aplicación funcional, elegante y
          con tecnología de vanguardia.
        </div>
        <router-link to="/portfolio" class="btn btn-primary">
          Ver Portafolio
        </router-link>
      </div>
      <div class="col-lg-6">
        <img src="@/assets/mockup.png" alt="" style="width: 100%" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home"
}
</script>

<template>
  <div class="custom-navbar custom-container">
    <div class="custom-navbar-brand">
      <a href="#">EspartaDevs</a>
    </div>
    <ul class="custom-navbar-nav">
      <li>
        <router-link to="/">Inicio</router-link>
      </li>
      <li>
        <router-link to="/portfolio">Portafolio</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
}
</script>

<style lang="scss">
@mixin reset-list {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
.custom-navbar {
  display: flex;
  align-items: center;
  height: 80px;
  border-bottom: 1px solid #cecece;
  background: #fff;
}
.custom-navbar-brand, .page-title {
  font-size: 20px;
  font-weight: 700;
  a {
    text-decoration: none;
    color: #000;
  }
}
.custom-navbar-nav {
  @include reset-list;
  display: none;
  flex-flow: row nowrap;
  margin-left: auto;
  li {
    font-weight: 500;
    margin-right: 55px;
    &:last-child {
      margin-right: 0;
    }
  }
  a {
    font-size: 15px;
    text-decoration: none;
    color: rgb(0, 89, 255);
  }
  @media(min-width: 768px){
    display: flex;
  }
}
</style>

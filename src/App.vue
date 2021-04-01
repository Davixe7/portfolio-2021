<template>
  <div id="app" class="sidenav-layout">
    <div class="sidenav">
      <div class="sidenav-brand">
        <img src="@/assets/espartadevs_isotype_black.png" />
      </div>
    </div>
    <div class="main">
      <Navbar />
      <div class="main-banner custom-container">
        <router-view />
      </div>
      <footer>
        <div class="custom-navbar custom-container">
          <div class="copy">
            © 2021 EspartaDevs, CA. Todos los derechos reservados
          </div>
          <ul class="custom-navbar-nav">
            <li>
              <a href="mailto:espartadevs@gmail.com">
                espartadevs@gmail.com
              </a>
            </li>
          </ul>
        </div>
      </footer>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";

export default {
  components: {
    Navbar,
  },
};
</script>


<style lang="scss">
@mixin reset-list {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
#app {
  display: flex;
  flex-flow: row nowrap;
}
.sidenav {
  display: none;
  flex: 1 0 80px;
  min-height: calc(100vh - 80px);
  width: 80px;
  border-right: 1px solid #cecece;
  top: 0;
  position: sticky;
  background: #fff;
  @media (min-width: 768px) {
    display: block;
  }
}
.sidenav-brand {
  height: 80px;
  border-bottom: 1px solid #cecece;
  display: flex;
  justify-content: center;
  align-items: center;
}
body {
  font-family: "Roboto", sans-serif;
  font-size: 14px;
  color: #2d2d2d;
  margin: 0;
  background: #efefef;
  @media (min-width: 768px) {
    font-size: 16px;
  }
}
h1,
h2,
h3,
h4 {
  margin: 0;
}
.w-100 {
  width: 100% !important;
}
.btn {
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
  border-radius: 3px;
  border: none;
  box-shadow: none;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
}
.btn-primary {
  font-size: 16px;
  color: #fff;
  padding: 15px 50px;
  background: #2D2D2D;
  width: fit-content;
}
.main {
  flex: 1 1 100%;
}
#app.sidenav-layout .custom-container {
  padding: 0 40px;
}
.section-title {
  font-weight: 700;
  margin-bottom: 25px;
}
.custom-container {
  width: 100% !important;
  padding: 0 25px;
  @media (min-width: 768px) {
    padding: 0 80px;
  }
}
.main-banner .col-lg-6 {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
  @media (min-width: 768px) {
    min-height: calc(100vh - 160px);
    padding-right: 40px;
  }
}
.main-banner h1 {
  font-size: 24px;
  font-weight: 900;
  max-width: 360px;
  margin: 0 0 18px 0;
  @media (min-width: 768px) {
    font-size: 42px;
  }
}
.main-banner .caption {
  font-size: 16px;
  line-height: 24px;
  margin-bottom: 25px;
  @media (min-width: 768px) {
    font-size: 20px;
    line-height: 32px;
  }
}
.main-banner-carousel {
  height: 100%;
}
footer {
  border-top: 1px solid #cecece;
}
.copy {
  font-size: 13px;
}
</style>

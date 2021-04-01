<template>
  <div class="portfolio-modal" v-if="project">
    <div class="portfolio-modal-actions">
      <span
        class="close-modal"
        @click="$emit('modalClosed')"
      >
        &times;
      </span>
    </div>
    <div class="modal-content container-fluid">
      <div class="row">
        <div class="col-lg-8 px-0">
          <div class="mockup-wrap">
            <img :src="`img/${project.captures[0]}`" style="width: 100%" alt="" />
          </div>
        </div>
        <div class="col-lg-4 px-0">
          <div class="modal-nav">
            <button
              class="btn"
              :disabled="!prevEnabled"
              @click="$emit('goPrev')"
            >
              Anterior
            </button>
            <button
              class="btn"
              :disabled="!nextEnabled"
              @click="$emit('goNext')"
            >
              Siguiente
            </button>
          </div>
          <div class="project-info">
            <h4 class="project-name">
              {{ project.name }}
            </h4>
            <div class="project-summary">
              {{ project.description }}
            </div>
            <a
              :href="project.url"
              target="_blank"
              class="btn btn-primary w-100"
              style="display: block; text-align: center"
            >
              Visitar sitio
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    project:{
      type: Object,
      default: ()=>({})
    },
    nextEnabled:{
      type: Boolean,
      default: false
    },
    prevEnabled:{
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss">
.portfolio-modal {
  // display: none;
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0,0,0,.5);
}
.portfolio-modal-actions {
  display: flex;
  width: calc(100% - 100px);
  padding: 20px 0;
  margin: 50px auto 0;
  .close-modal {
    color: #fff;
    font-size: 28px;
    font-weight: 500;
    margin-left: auto;
    cursor: pointer;
  }
}
.portfolio-modal .modal-content {
  width: calc(100% - 100px);
  margin: 0 auto;
  border-radius: 3px;
  overflow: hidden;
  background: #fff;
}
.portfolio-modal .mockup-wrap {
  height: 500px;
  overflow: auto;
  background: lightgray;
  padding: 40px;
  background: #9ab8b0;
  img {
    border-radius: 3px;
    box-shadow: 0 2px 20px 3px rgba(0,0,0,.25);
  }
}
.modal-nav {
  display: flex;
  flex-flow: row nowrap;
  border-bottom: 1px solid #cecece;
}
.modal-nav .btn {
  flex: 1 1 auto;
  padding: 20px;
  border-radius: 0;
  background: #fff;
  &:first-child {
    border-right: 1px solid #cecece;
  }
}
.portfolio-modal .project-info {
  padding: 20px;
  .project-name {
    margin-bottom: 15px;
  }
  .project-summary {
    font-size: 14px;
    line-height: 24px;
    margin-bottom: 20px;
  }
}
</style>

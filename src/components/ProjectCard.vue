<template>
  <div class="project-card" v-if="project">
    <div class="img">
      <img :src="captureUrl" alt="" />
    </div>
    <div class="project-title">
      <div class="project-name">
        {{ project.name }}
      </div>
      <div class="project-type">
        {{ project.type }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed:{
    captureUrl(){
      if( !this.project.captures[0] ){ return '' }
      return `/img/340/${this.project.captures[0]}`
    }
  },
  props: {
    project:{
      type: Object,
      default: ()=>({})
    }
  }
};
</script>

<style lang="scss">
.project-card {
  position: relative;
  height: 240px;
  margin-bottom: 30px;
  padding: 20px;
  // border: 1px solid gray;
  border-radius: 3px;
  background: #fff;
  box-shadow: 0 2px 10px 1px rgba(0,0,0,.05);
}
.project-card .img {
  height: 150px;
  border-radius: 2px;
  overflow: hidden;
  img {
    max-width: 100%;
  }
}
.project-title {
  position: absolute;
  left: 20px;
  right: 20px;
  bottom: 20px;
}
.project-name {
  font-size: 16px;
  font-weight: 700;
  margin-bottom: 5px;
}
.project-type {
  font-size: 12px;
}
</style>
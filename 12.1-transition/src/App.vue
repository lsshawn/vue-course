<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Animations</h1>

        <hr />

        <button class="btn btn-primary" @click="show = !show">
          Show Alert
        </button>

        <br /><br />

        <transition name="fade">
          <div class="alert alert-info" v-if="show">Info</div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
    };
  },
};
</script>

<style scoped>
.fade-enter {
  opacity: 0;
}

.fade-enter-active {
  transition: opacity 1s;
  /* you don't need opacity: 1 */
}

.fade-leave {
  /* you don't need opacity: 1. That's the default */
}

.fade-leave-active {
  transition: opacity 1s;
  opacity: 0;
}
</style>

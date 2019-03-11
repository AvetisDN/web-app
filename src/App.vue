<template>
  <div id="app">
    <Menu name="My Web App"/>

    <main class="container my-4">
      <div class="row">
        <div class="col col-lg-9">
          <transition :name="transitionName">
            <router-view class="child-view"/>
          </transition>
        </div>
        <div class="col col-lg-3">
          Sidebar
        </div>
      </div>
    </main>
    <Footer/>

  </div>
</template>

<style>
/* .router-link-exact-active */
.page {
  padding: 60px 0 60px 0;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s ease;
}
.fade-enter, .fade-leave-active {
  opacity: 0;
}
.child-view {
  position: absolute;
  transition: all .5s cubic-bezier(.55,0,.1,1);
}
.slide-left-enter, .slide-right-leave-active {
  opacity: 0;
  -webkit-transform: translate(30px, 0);
  transform: translate(30px, 0);
}
.slide-left-leave-active, .slide-right-enter {
  opacity: 0;
  -webkit-transform: translate(-30px, 0);
  transform: translate(-30px, 0);
}
</style>

<script>
import Menu from "./components/Menu"
import Footer from "./components/Footer"

export default {
  name: 'app',
  components: {
    Menu, Footer
  },
  watch: {
  '$route' (to, from) {
    const toDepth = to.path.split('/').length
    const fromDepth = from.path.split('/').length
    this.transitionName = toDepth < fromDepth ? 'slide-right' : 'slide-left'
  }
}
}
</script>
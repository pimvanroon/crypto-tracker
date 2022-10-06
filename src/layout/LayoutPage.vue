<template>
  <div class="layout-container">
      <transition name="fade" mode="out-in">
        <keep-alive include="dashboard">
          <router-view />
        </keep-alive>
      </transition>
  </div>
</template>
<script>
export default {
  name: 'LayoutPage',
  data() {
    return {
      currentPage: 'dashboard'
    }
  },
  watch: {
    '$route': {
      deep: true,
      handler: function (page) {
        this.currentPage = page.name;
      }
    }
  }
}
</script>
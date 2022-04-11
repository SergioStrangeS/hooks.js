<template>
  <!--  <nav>-->
  <!--    <router-link to="/">Home</router-link> |-->
  <!--    <router-link to="/about">About</router-link>-->
  <!--  </nav>-->

  <NavbarMenu
    :localdata="localdata"
    @isDarkTheme="DarkTheme"
  />

  <section class="min-vh-100" :class="localdata.darkTheme ? 'bg-dark text-light' : null">
      <router-view :localdata="localdata"/>
  </section>
</template>

<style scoped>
  .main-enter-active,
  .main-leave-active {
    transition: .5s;
  }

  .main-enter,
  .main-leave-to {
    opacity: 0;
  }
</style>

<script lang="ts">
import NavbarMenu from '@/components/NavbarMenu.vue'

export default {
  components: {
    NavbarMenu
  },
  data () {
    return {
      localdata: {
        Kinopoisk: {
          item: null,
          show: false
        },
        Discord: {
          item: null,
          show: false
        },
        Together: null,
        darkTheme: null,
        historyItems: [],
        agree: false
      },
      url: ''
    }
  },
  methods: {
    DarkTheme: function (isDark) {
      console.log(isDark)
      this.localdata.darkTheme = isDark
    }
  }
}
</script>

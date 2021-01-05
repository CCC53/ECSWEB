<template>
  <v-app>
    <Header @open-drawer="openDrawer()" />
    <MobileMenu v-model="drawerStatus" />
    <v-main>
        <nuxt />
    </v-main>
    <FooterPlaceholder/>
    <Footer/>
  </v-app>
</template>

<script>
import Header from '~/components/Header.vue';
import FooterPlaceholder from '~/components/FooterPlaceholder.vue';
import Footer from '~/components/Footer.vue';
import MobileMenu from '~/components/MobileMenu';
export default {
  components: {
    Header,
    FooterPlaceholder,
    Footer,
    MobileMenu
  },
  data() {
    return {
      drawerStatus: false,
    }
  },
  methods: {
    openDrawer () {
      this.drawerStatus = true;
      console.log('menu')
    }
  }
}
</script>

<style lang="scss">
.v-application{
  .v-application--wrap{
    z-index: 100;
    .v-main{
      background: #fff;
    }
  }
}
</style>
<template>
  <div class="header d-flex align-center" :class="{ scrolled_color: scrollPosition > 50 }">
    <v-btn text class="logoContainer" nuxt to="/">
      <img src="/LOGO.png" alt="">
    </v-btn>
    <div class="navLinks d-none d-md-flex align-center">
        <v-btn dark text nuxt to="/">Inicio</v-btn>
        <v-btn dark text nuxt to="nosotros">Nosotros</v-btn>
        <v-btn dark text nuxt to="clientes">Clientes</v-btn>
        <v-btn dark text nuxt to="contacto">Contacto</v-btn>
    </div>
    <v-btn class="btn d-block d-md-none" icon @click.stop="$emit('open-drawer')">
        <img src="/icons/menu.png" alt="">
    </v-btn>
  </div>
</template>

<script>
export default {
  data: () => ({
    scrollPosition: null
  }),
  mounted () {
    window.addEventListener("scroll", this.updateScrollPosition);
  },
  methods: {
    updateScrollPosition () {
      this.scrollPosition = window.scrollY;
    }
  }
};
</script>

<style lang="scss" scoped>
  .header {
        background-color: transparent;
        justify-content: space-between;
        height: 4em;
        position: fixed;
        transition: all 0.3s 0s ease-in;
        width: 100%;
        z-index: 800;
        &.scrolled_color {
        height: 5em;
        background-color: black;
        .logoContainer {
          img {
            height: 3.5em;
          }
        }
      }
      .logoContainer {
        height: auto !important;
        padding: 0 8px;
        img {
          transition: all 0.3s 0s ease-in;
          height: 4em;
          width: auto;
        }
      }
      .btn {
      height: auto;
      width: auto;
      img {
        height: 4em;
        width: auto;
      }
    }
  }
  @media (min-width: 768px) and (max-width: 992px) {
    .header {
      justify-content: flex-start;
    }
    .btn {
      margin-left: 41em;
    }
  }
  @media (max-width: 600px) {
    .header {
      justify-content: flex-start;
      .logoContainer {
        img {
          height: 3.5em;
        }
      }
      &.scrolled_color {
        .logoContainer {
          img {
            height: 3em;
          }
        }
      }
    }
    .btn {
      margin-left: 18em;
    }
  }
  @media (max-width: 375px) {
    .header {
      justify-content: flex-start;
      .logoContainer {
        img {
          height: 3.5em;
        }
      }
      &.scrolled_color {
        .logoContainer {
          img {
            height: 3em;
          }
        }
      }
    }
    .btn {
      margin-left: 14em;
    }
  }
</style>
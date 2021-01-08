<template>
  <v-navigation-drawer v-model="menuStatus" app right disable-resize-watcher hide-overlay class="sidenav">
    <div class="navigationContentWraper d-flex flex-column justify-space-between">
      <div class="sidetop d-flex align-center justify-space-between">
        <img src="../static/LOGO.png" alt="Logo" />
        <v-btn icon @click="$emit('input', false)" class="btn">
          <img src="../static/icons/close.svg" alt="Menu" />
        </v-btn>
      </div>
      <div class="links d-flex flex-column align-end">
        <v-btn text x-large nuxt to="/">Inicio</v-btn>
        <v-btn text x-large nuxt to="/nosotros">Nosotros</v-btn>
        <v-btn text x-large nuxt to="/clientes">Clientes</v-btn>
        <v-btn text x-large nuxt to="/contacto">Contacto</v-btn>
      </div>
      <div class="sidebottom">
        <p>Iztacalco <br />CDMX.</p>
        <div class="d-flex">
          <img src="/icons/gmail.svg" alt="Phone" />
          <p>Efficientcustomsoft@gmail.com</p>
        </div>
      </div>
    </div>
  </v-navigation-drawer>
</template>


<script>
export default {
  props: {
    value: Boolean,
  },
  watch: {
    value(value) {
      console.log('value value', value);
      this.menuStatus = value;
    },
    menuStatus(value) {
      console.log('menuStatus value', value);
      this.$emit('input', value);
    }
  },
  data() {
    return {
      menuStatus: false
    }
  }
};
</script>

<style lang="scss" scoped>
.sidenav {
  width: 100% !important;
  z-index: 900;
  .navigationContentWraper {
    height: 100vh;
    width: 100%;
    position: relative;
    z-index: 100;
    .backgroundImage{
      position: absolute;
      z-index: -100;
      top: 50%;
      left: -50%;
      width: 100%;
      transform: translateY(-50%);
    }
  }
  .sidetop {
    padding: 1.5em 32px;
    img {
      height: 3em;
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
  .links {
    padding: 5% 10% 0;
    .v-btn {
      color: grey;
      text-transform: none;
      letter-spacing: 1px;
      font-size: 1.7em;
      font-weight: bold;
    }
  }
  .sidebottom {
    padding: 5% 10% 2em;
    color: grey;
    img {
      height: 1.5em;
    }
  }
}
</style>
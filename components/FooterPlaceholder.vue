<template>
    <div class="footerPlaceholder"></div>
</template>

<style lang="scss" scoped>
.footerPlaceholder {
  width: 100%;
  opacity: 0;
  pointer-events: none;
  margin-bottom: 30em;
  z-index: -100;
}
@media (max-width: 600px) {
  .footerPlaceholder {
    margin-bottom: 50em;
  }
}
</style>
<template>
    <div class="header d-flex justify-center align-center" :style="{ 'background-image': 'url(' + config.image + ')' }">
        <h1>{{config.title}}</h1>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: 'pageHeader',
    props: ['config']
});
</script>

<style lang="scss" scoped>
    .header {
        background-position: center;
        background-size: cover;
        color: white;
        height: 20em;
    }
    @media (max-width: 600px) {
        .header {
            width: 100%;
        }
    }
</style>
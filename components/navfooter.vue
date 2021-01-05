<template>
    <div class="nav d-flex justify-space-around align-center">
        <div class="content">
            <h2>Conoce nuestros clientes</h2>
            <v-btn outlined color="white" nuxt to="clientes">Clientes</v-btn>
        </div>
        <div class="content">
            <h2>Contactanos</h2>
            <v-btn outlined color="white" nuxt to="contacto">Contacto</v-btn>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .nav {
        background-color: grey;
        height: 20em;
        margin-top: 1em;
    }
    .content {
        color: white;
        text-align: center;
        h2 {
            margin-bottom: 0.5em;
        }
        .v-btn {
            width: 100%;
        }
    }
    @media (max-width: 600px) {
        .nav {
            flex-direction: column;
        }
    }
</style>
<template>
    <div>
        <pageHeader :config="config"/>
        <div class="clientsContainer">
            <h2>Algunos de nuestros clientes</h2>
            <div class="clientsLogos">
                <div class="logos d-flex justify-space-around">
                    <v-btn text class="btn" href="https://www.inegi.org.mx" target="_blanck">
                        <img src="clients/INEGI.png" alt="">
                    </v-btn>
                    <v-btn text class="btn" href="https://www.metlife.com.mx" target="_blanck">
                        <img src="clients/metlife_logo.png" alt="">
                    </v-btn>
                    <v-btn text class="btn" href="https://assetel.com" target="_blanck">
                        <img src="clients/AssetelLogo.png" alt="">
                    </v-btn>
                </div>
                <div class="logos2 d-flex justify-space-around">
                    <v-btn text class="btn" href="https://www.minifab3d.net" target="_blanck">
                        <img src="clients/1b59f2_769eea39ee294388b45f89515b63a54b-removebg-preview.png" alt="">
                    </v-btn>
                    <v-btn text class="btn" href="https://vivoxie.com/es/index" target="_blanck">
                        <img src="clients/download-removebg-preview.png" alt="">
                    </v-btn>
                    <v-btn text class="btn" href="https://tec.mx/es" target="_blanck">
                        <img src="clients/unnamed-removebg-preview.png" alt="">
                    </v-btn>
                </div>
            </div>
        </div>
        <div class="successStories">
            <h2>Algunos de nuestros proyectos más destacados</h2>
            <v-simple-table class="table">
                <thead>
                  <tr>
                    <th class="text-left">Empresa</th>
                    <th class="text-left">Descripción</th>
                    <th class="text-left">Resultado</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(project, i) in projects" :key="i">
                    <td>
                        <img class="logo" :src="project.empresa" alt="">
                    </td>
                    <td>{{project.description}}</td>
                    <td>
                        <a :href="project.link" target="_blanck">Link resultante</a>
                    </td>
                  </tr>
                </tbody>
            </v-simple-table>
        </div>
        <div class="contactBar d-flex justify-center align-center flex-column">
            <h1>¿Tienes dudas?</h1>
            <v-btn outlined color="white" nuxt to="contacto">Contactanos</v-btn>
        </div>
    </div>
</template>

<script>
import pageHeader from '~/components/page-header.vue';
export default {
    name: 'clientes',
    components: {
        pageHeader
    },
    data() {
        return {
            config: {
                title: 'Clientes',
                image: '/page-header/clients.jpg'
            },
            projects: [{
                empresa: 'success/pips.png',
                description: 'Desarrollo del sitio web oficial',
                link: 'https://www.pipstechnology.com'
            }, {
                empresa: 'success/logo.png',
                description: 'Desarrollo del sitio web oficial',
                link: 'https://www.greenteammx.com'
            }, {
                empresa: 'success/cuentame.png',
                description: 'Desarrollo de la plataforma para tomar teoria psicologica',
                link: 'https://sicuentame.com'
            }, {
                empresa: 'success/tec.png',
                description: 'Desarrollo de la aplicacion movil para dar a conocer las carreras',
                link: 'https://play.google.com/store/apps/details?id=com.itesm.conoceeltec'
            }]
        }
    },   
}
</script>

<style lang="scss" scoped>
    .clientsContainer {
        h2 {
            text-align: center;
            margin: 2em 0em;
        }
    }
    .btn {
        height: 8em !important;
        img {
            height: 8em;
        }
    }
    .logos {
        margin-bottom: 3em;
    }
    .successStories {
        h2 {
            margin: 3em 0em 1em 0em;
            text-align: center;
        }
        .table {
            margin: 0 auto;
            width: 95%;
        }
    }
    a {
        text-decoration: none;
        color: black !important;
    }
    a:hover {
        color: rgb(189, 189, 44) !important;
    }
    .logo {
        height: 6em;
        padding: 0.8em 0em;
    }
    .contactBar {
        background-color: grey;
        color: white;
        height: 20em;
        margin-top: 2em;
        .v-btn:hover {
            color: white !important;
        }
    }
    @media (min-width: 768px) and (max-width: 992px) {
        .clientsContainer {
            h2 {
                margin: 1em 0em;
            }
        }
        .btn {
            height: 4em !important;
            img {
                height: 4em;
            }
        }
        .successStories {
            h2 {
                margin: 1.5em 0em 1em 0em;
            }
        }
        .table {
            margin: 0 auto;
            width: 90% !important;
        }
        .logo {
            height: 4em;
            padding: 0.7em 0em;
        }
        a {
            font-size: 0.9em !important;
        }
        td {
            font-size: 0.8em !important;
        }
    }
    @media (max-width: 600px) {
        .clientsContainer {
            h2 {
                margin: 0.7em 0em;
            }
        }
        .btn {
            height: 5em !important;
            img {
                height: 5em;
            }
        }
        .logos {
            flex-direction: column;
        }
        .logos2 {
            flex-direction: column;
        }
        .successStories {
            h2 {
                margin: 0.9em 0em 0.5em 0em;
            }
        }
        .table {
            width: 90% !important;
        }
        .logo {
            height: 4em;
            padding: 0.5em 0em;
        }
        a {
            font-size: 1em !important;
        }
        td {
            font-size: 0.7em !important;
        }
    }
    @media (max-width: 400px) {
        .successStories {
            td {
                font-size: 0.57em !important;
            }
        }
    }
</style>
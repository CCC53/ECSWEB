<template>
    <div>
        <div class="header d-flex align-center justify-center flex-column">
            <h1>Efficient Custom Software</h1>
            <h2>Software Eficiente a la Medida</h2>
        </div>
        <div class="productsContainer">
            <h1 class="title">Nuestros Productos</h1>
            <v-carousel cycle height="300" hide-delimiter-background show-arrows-on-hover interval="2000">
                <v-carousel-item v-for="(product, i) in products" :key="i">
                  <v-sheet color="rgb(184, 169, 169)" height="100%">
                    <v-row class="fill-height" align="center" justify="center">
                        <h1 class="product">{{product}}</h1>
                    </v-row>
                  </v-sheet>
                </v-carousel-item>
            </v-carousel>
        </div>
        <div class="servicesContainer">
            <h1 class="servicesTitle">Nuestros Servicios</h1>
            <v-expansion-panels popout>
                <v-expansion-panel v-for="(service, i) in services" :key="i">
                    <v-expansion-panel-header>{{service.title}}</v-expansion-panel-header>
                        <v-expansion-panel-content>
                            <div class="services d-flex justify-center align-center">
                                <p>{{service.body}}</p>
                                <br>
                                <img :src="service.image" class="service">
                            </div>
                        </v-expansion-panel-content>
                </v-expansion-panel>
            </v-expansion-panels>
        </div>
        <navfooter/>
    </div>
</template>

<script>
import navfooter from '~/components/navfooter';
export default {
    components: {
        navfooter
    },
    data() {
        return {
            products: ['Servicios a la medida', 'Aplicaciones administrativas', 'Herramientas para portales', 'Desarrollo Web', 'Seguridad',
                        'Innovación en la administración pública', 'Herramientas de desarrollo', 'Bases de datos', 
                        'Sistemas informáticos para aumentar la eficiencia de las empresas', 'Sistemas informáticos para aumentar la competitividad de las empresas'],
            services: [{
                title: 'Desarrollo de software a medida',
                body: 'Diseñamos y creamos herramientas informáticas basadas en necesidades particulares de nuestros clientes. Analizamos las característicasde la compañía en busca de optimizar aquellos procesos clave para el negocio. en la creación El resultado de este análisis resulta de un sistema a medida que impacte de forma directa o indirecta en las ganancias de la empresa.',
                image:'/services/desarrollo.png'
            }, {
                title: 'Consultoría',
                body: 'Cuando un cliente tiene un problema que requiere un análisis a fondo, acudimos al negocio para encargarnos de hacer una revisión, detectar errores internos y dar las pautas para remediar el problema.',
                image: '/services/consultoria.png'
            }, {
                title: 'Auditoría',
                body: 'Recogemos, agrupamos y evaluamos evidencias para estudiar los mecanismos de control que están implantados en la empresa de nuestros clientes, determinando si los mismos son adecuados y cumplen unos determinados objetivos o estrategias, estableciendo los cambios que se deberían realizar para la consecución de estos. Optimizamos el funcionamiento de cualquier entidad.',
                image: '/services/auditoria.png'
            }]
        }
    }
}
</script>

<style lang="scss" scoped>
    .header {
        background-image: url('/page-header/home.jpg');
        background-position: center;
        background-size: cover;
        color: white;
        height: 25em;
    }
    .productsContainer {
        margin-top: 2em;
        .title {
            font-size: 2.5em !important;
            font-weight: 600;
            margin: 1.5em 0em 0.5em 0em;
            text-align: center;
        }
        .v-carousel {
            width: 97%;
            margin: 0 auto;
            .product {
                text-align: center;
            }
        }
    }
    .servicesContainer {
        margin-bottom: 4em;
        .servicesTitle {
            font-size: 2.5em !important;
            margin: 1em 0em 0.2em 0em;
            text-align: center;
        }
        .v-expansion-panels {
            margin: 0 auto;
            width: 95%;
            .v-expansion-panel {
                color: black;
                background-color: rgb(194, 188, 188);
                text-align: center;
                p {
                    text-align: left !important;
                }
                .service {
                    height: 15em;
                    text-align: center;
                }
            }
        }
    }
    @media (max-width: 600px) {
        .productsContainer {
            .title {
                text-align: center !important;
                font-size: 1.6em !important;
            }
        }
        .v-carousel {
            width: 95% !important;
            .v-sheet {
                height: 104% !important;
            }
            .product {
                font-size: 1em !important;
                text-align: center;
            }
        }  
        .v-item-group {
            text-align: center;
        }
        .servicesContainer {
            .servicesTitle {
                font-size: 1.6em !important;
            }
            .services {
                flex-direction: column;
            }
        }
    }
    @media(max-width:400px) {
        .header {
            text-align: center !important;
        }
        .servicesContainer {
            .services {
                flex-direction: column;
            }
        }
    }
</style>
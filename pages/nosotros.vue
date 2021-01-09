<template>
    <div>
        <pageHeader :config="config"/>
        <v-carousel cycle height="400" hide-delimiter-background show-arrows-on-hover>
            <v-carousel-item v-for="(slide, i) in slides" :key="i">
              <v-sheet :color="color" height="100%">
                <v-row class="fill-height" align="center" justify="center">
                    <div class="incContainer d-flex flex-column justify-center align-center">
                        <div class="display-3">
                            <h4>{{slide.title}}</h4>
                        </div>
                        <p>{{slide.body}}</p>
                    </div>
                </v-row>
              </v-sheet>
            </v-carousel-item>
        </v-carousel>
        <h1>Fundadores</h1>
        <div class="membersContainer d-flex">
            <v-card class="mx-auto my-12" max-width="300" v-for="(member, i) in members" :key="i">
                <v-img height="250" :src="member.image"></v-img>
                <v-card-title>{{member.name}}</v-card-title>
                <v-card-text>
                    <p>{{member.info}}</p>
                </v-card-text>
            </v-card>
        </div>
        <div class="docsContainer">
            <h1>Documentación</h1>
            <v-list dense>
              <v-subheader>Documentos para PROSOFT</v-subheader>
              <v-list-item-group color="primary">
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
                <v-list-item>
                  <v-list-item-content>
                    <v-list-item-title>Penny</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
        </div>
        <navfooter/>
    </div>
</template>

<script>
import pageHeader from '~/components/page-header';
import navfooter from '~/components/navfooter';
export default {
    name: 'nosotros',
    components: {pageHeader, navfooter},
    data() {
        return {
            config: {
                image: '/page-header/ours.jpg',
                title: 'Nosotros'
            },
            color: '#9a9a9a',
            slides: [{
                title: 'Acerca de la empresa',
                body: 'Efficient Custom Software (ECS) es una empresa mexicana de base tecnológica especializada en el desarrollo e integración de soluciones de software mediante  el desarrollo de software a la medida. Fundada en 2020 con la experiencia obtenida ha generado soluciones diseñadas y desarrolladas tanto para el uso de la administración pública como para el servicio de la industria en plataforma digital. Nuestra compañía la integran especialistas altamente capacitados y con estudios que avalan su desempeño profesional de manera integral lo que garantiza una fuerza de trabajo colaborativa y dinámica. Realizamos páginas web a la medida así como el desarrollo de aplicaciones, desarrollo de software, consultoria y auditoria.'
            },{
                title: 'Nuestro objetivo',
                body: 'Desarrollar sistemas eficientes, intuitivos y fáciles de manejar para el sector público o privado.'
            }],
            members: [{
                name: 'Daniel Suarez',
                info: 'Estudia actualmente la carrera de Ingeniería en Informática en el UPIICSA IPN. Destaca por su habilidad en la programación y su entendimiento así como también en el diseño de páginas web y el manejo de base de datos, teniendo un gran desempeño en trabajo en equipo. Completando sus actividades académicas con el estudio del idioma inglés y tomando cursos de distintos lenguajes de programación como python.',
                image: '/members/dsg.jpeg'
            },{
                name: 'Abel Durán',
                info: 'Estudia actualmente la carrera de Ingeniería en Informática en el UPIICSA IPN. Destaca por su habilidad en la programación y diseño de páginas web. Completando sus actividades académicas con el estudio del idioma inglés y tomando cursos de distintos lenguajes de programación como C++. También tiene estudios previos de hidráulica, mecánica, electricidad y electrónica.',
                image: '/members/aidc.jpeg'
            }, {
                name: 'Andrés Hernández',
                info: 'Estudia actualmente la carrera de Ingeniería en Informática en el UPIICSA IPN. Destaca por su habilidad en la programación y su entendimiento así como también en el diseño de páginas web y con una buena facilidad de palabra, teniendo un gran desempeño en trabajo en equipo. Completando sus actividades académicas con el estudio del idioma inglés y tomando cursos de distintos lenguajes de programación como C++ u otros temas con relación a la carrera. Con un gran gusto en las matemáticas y a la lectura, así como a los videojuegos y series/peliculas.',
                image: '/members/ahl.jpeg'
            }, {
                name: 'Iván García',
                info: 'Estudia actualmente la carrera de Ingeniería en Informática en el UPIICSA IPN. Destaca por su habilidad en la programación y su entendimiento así como también en el diseño de páginas web, teniendo un gran desempeño en trabajo en equipo. Completando sus actividades académicas con el estudio del idioma inglés y tomando cursos de distintos lenguajes de programación como C++.',
                image: '/members/igv.jpeg'
            }, {
                name: 'Carlos Calette',
                info: 'Estudia actualmente la carrera de Ingeniería en Informática en UPIICSA IPN. Se destaca su conocimiento en desarrollo front-end con Vue y Angular, desarrollo de back-end en Node, Flask y GraphQL, manejo de bases de datos NoSQL. Completando sus actividades académicas con el estudio del idioma inglés y tomando cursos de desarrollo móvil con Flutter.',
                image: '/members/ccc.jpg'
            }]
        }
    }    
}
</script>

<style lang="scss" scoped>
    .v-carousel {
        margin: 4em auto 0em auto;
        width: 95%;
    }
    .incContainer {
        p {
            padding: 0em 3em;
            margin-top: 1em;
        }
    }
    h1 {
        margin-top: 0.5em;
        text-align: center;
    }
    .membersContainer {
        width: 95%;
        margin: -1em auto;
    }
    .v-list {
        width: 95%;
        margin: 0 auto;
    }
    @media (min-width: 768px) and (max-width: 992px) {
        .v-carousel {
            margin: 2em auto 0em auto;
            height: 150% !important;
        }
        .membersContainer {
            flex-wrap: wrap;
        }
    }
    @media (max-width: 600px) {
        .v-carousel {
            margin: 1em auto 0em auto;
        }
        .incContainer {
            // padding: 3em 0em;
            h4 {
                text-align: center;
                font-size: 0.5em;
            }
            p {
                font-size: 0.85em;
            }
        }
        .membersContainer {
            flex-direction: column;
        }
  }

  @media (max-width: 400px) {
    .v-carousel {
      height: 150% !important;
      h4 {
        margin-bottom: -0.8em !important;
      }
      p {
        font-size: 0.8em;
      }
    }
    .incContainer {
      padding: 0em 0em 9em 0em;
    }
  }
</style>
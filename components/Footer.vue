<template>
    <v-layout class="footerContainer d-flex align-center justify-space-around">
        <v-btn text class="logoContainer" nuxt to="/">
            <img src="/LOGO.png" alt="">
        </v-btn>
        <div class="infoContainer">
            <p>Iztacalco<br>CDMX</p>
            <div class="mail">
                <p>Correo</p>
                <v-btn text dark small target="_black" href="mailto:Efficientcustomsoft@gmail.com" class="ml-n4">
                    <div class="emaillogo d-flex align-center">
                        <img src="icons/gmail.svg" alt="">
                        <span>Efficientcustomsoft@gmail.com</span>
                    </div>
                </v-btn>
            </div>
            <div class="btnContainer d-flex">
                <v-btn icon href="https://www.facebook.com/Efficient-Custom-Soft-104889598111597/" target="_blanck">
                    <img src="/icons/facebook.svg" alt="">
                </v-btn>
                <v-btn icon href="https://www.instagram.com/efficientcustomsoft/" target="_blanck">
                    <img src="/icons/instagram.svg" alt="">
                </v-btn>
                <v-btn icon href="https://twitter.com/EfficientCSoft" target="_blanck">
                    <img src="/icons/twitter.svg" alt="">
                </v-btn>
            </div>
        </div>
        <div class="linksContainer d-flex flex-column">
            <v-btn text dark nuxt to="/">Inicio</v-btn>
            <v-btn text dark nuxt to="nosotros">Nosotros</v-btn>
            <v-btn text dark nuxt to="clientes">Clientes</v-btn>
            <v-btn text dark nuxt to="contacto">Contacto</v-btn>
        </div>
    </v-layout>    
</template>

<style lang="scss" scoped>
    .footerContainer {
        color: white;
        height: 30em;
        width: 100%;
        position: fixed;
        bottom: 0;
        background-color: black;
        z-index: -100;
        .logoContainer {
            height: 10em;
            img {
                height: 8em;
            }
        }
        .mail {
            p {
                margin-bottom: 0em;
            }
        }
        .btnContainer {
            margin-top: 1em;
        }
        .linksContainer {
            align-items: flex-start;
        }
    }
    @media (min-width: 768px) and (max-width: 992px) {
        .footerContainer {
            .logoContainer {
                height: 8em;
                img {
                    height: 6em;
                }
            }
        }
    }
    @media (max-width: 600px) {
        .footerContainer {
            flex-direction: column;
            height: 50em;
            .infoContainer {
                align-items: center;
                display: flex;
                flex-direction: column;
                text-align: center;
            }
            .linksContainer {
                align-items: center;
            }
        }
    }
</style>
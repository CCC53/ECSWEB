<template>
    <div>
        <pageHeader :config="config" />
        <div class="contactContainer d-flex justify-space-around">
            <div class="contactInfo">
                <h2>Contactanos</h2>
                <div class="d-flex btn">
                    <img src="icons/facebook.svg" alt="" class="icon">
                    <a href="https://www.facebook.com/Efficient-Custom-Soft-104889598111597/" target="_blanck" class="link">Facebook</a>
                </div>
                <div class="d-flex btn">
                    <img src="icons/twitter.svg" alt="" class="icon">
                    <a href="https://twitter.com/EfficientCSoft" target="_blanck" class="link">Twitter</a>
                </div>
                <div class="d-flex btn">
                    <img src="icons/instagram.svg" alt="" class="icon">
                    <a href="https://www.instagram.com/efficientcustomsoft/" target="_blanck" class="link">Instagram</a>
                </div>
                <div class="d-flex btn">
                    <img src="icons/gmail.svg" alt="" class="icon">
                    <a href="mailto:Efficientcustomsoft@gmail.com" target="_blanck" class="link">Correo</a>
                </div>
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3763.380914851523!2d-99.09402488464141!3d19.395941086905193!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x85d1fc2e3efc321b%3A0xabf8454acb3a3a99!2sUPIICSA%20%E2%80%93%20Unidad%20Profesional%20Interdisciplinaria%20de%20Ingenier%C3%ADa%20y%20Ciencias%20Sociales%20y%20Administrativas%20IPN!5e0!3m2!1ses-419!2smx!4v1608935885490!5m2!1ses-419!2smx" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
            </div>
            <v-form @submit="send" v-model="valid" ref="form">
                <v-text-field placeholder="Nombre" label="Nombre" v-model="formData.name" :rules="nameRules"></v-text-field>
                <v-text-field placeholder="Email" label="Email" v-model="formData.email" :rules="emailRules"></v-text-field>
                <v-select :items="tipo" label="Sector" v-model="formData.sector"></v-select>
                <v-text-field placeholder="Nombre de la empresa" label="Nombre de la empresa" v-model="formData.company"></v-text-field>
                <v-select :items="empresa" label="Tipo de empresa" v-model="formData.companyType"></v-select>
                <v-textarea label="Dejanos un mensaje" v-model="formData.message"></v-textarea>
                <v-btn  type="submit" color="primary" class="submit" :disabled="!valid || loading">Enviar</v-btn>
            </v-form>
            <v-dialog v-model="dialog" persistent width="400">
                <v-card>
                  <v-card-title v-if="loading">Cargando...</v-card-title>
                  <v-card-title v-if="!loading && !err">Enviado correctamente</v-card-title>
                  <v-card-title v-if="!loading && err">Error de envio, prueba de nuevo.</v-card-title>
                  <v-card-text>
                    <v-progress-linear v-if="loading" indeterminate></v-progress-linear>
                    <v-btn v-if="!loading" style="margin-top: 2em" @click="dialog = !dialog">Cerrar</v-btn>
                  </v-card-text>
                </v-card>
            </v-dialog>
        </div>
    </div>
</template>

<script>
import pageHeader from '~/components/page-header.vue';
export default {
    components: { pageHeader },
    name: 'contacto',
    data() {
        return {
            config: {
                title: 'Contacto',
                image: '/page-header/contact_header_desktop.jpg'
            },
            formData: {
                name: '',
                email: '',
                sector: '',
                company: '',
                companyType: '',
                message: ''
            },
            nameRules: [(v) => !!v || "El nombre es obligatorio"],
            emailRules: [
                (v) => !!v || "El email es obligatorio",
                (v) => /.+@.+\..+/.test(v) || "Ingresa un email valido",
            ],
            tipo: ["Particular", "Empresa"],
            empresa: [
                "Abarrotes",
                "Autoservicio",
                "Hotel/Restaurante",
                "Mayorista",
                "Minorista",
                "Tienda de conveniencia",
                "Tienda de especialidades",
                "Tienda departamental",
                "No aplica",
            ],
            valid: false,
            loading: false,
            dialog: false,
            err: false
        }
    },
    methods: {
        async send(e) {
            e.preventDefault();
            if (this.valid) {
                this.dialog = true;
                this.loading = true;
                const url = 'https://jsonplaceholder.typicode.com/posts';
                const data = JSON.stringify(this.formData);
                try {
                    const response = await fetch(url, {method:'POST', body:data, headers:{'Content-type': 'application/json; charset=UTF-8'}});
                    const data = await response.json();
                    console.log(data);
                    this.err = false;
                } catch (error) {
                    console.log(error.message);
                    this.err = true;
                }
                this.loading = false;
                this.$refs.form.reset();
            }
        }
    }
}
</script>

<style lang="scss" scoped>
    .contactContainer {
        margin: 3em 0em;
    }
    .btn {
        margin: 1em 0em;
    }
    .v-form {
        width: 40%;
    }
    .submit {
        margin-top: 2em;
        width: 100%;
    }
    .link {
        color: #c0c0c0;
        text-decoration: none;
    }
    .icon {
        margin-right: 0.4em;
    }
    .link:hover {
        color: #cbcbcb;
    }
    @media (min-width: 768px) and (max-width: 992px) {
        .contactContainer {
            flex-direction: column;
            margin: 2em 3em;
        }
        .v-form {
            margin-top: 1em;
            width: 100%;
        }
        iframe {
            width: 100% !important;
        }
    }
    @media (max-width: 600px) {
        .contactContainer {
            flex-direction: column;
            margin: 1em 2em;
        }
        iframe {
            width: 100% !important;
        }
        .v-form {
            margin-top: 1em;
            width: 100%;
        }
    }
</style>
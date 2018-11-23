<template>
  <q-page class="flex-center">
     <img class ="Imagen" alt="Quasar logo" src="~assets/Logo.jpg">
    <h1 class="Titulos"> Ingrese los siguientes datos para recuperar su contraseña</h1>
    <div class ="contenedor">
  <q-input class ="inputs" v-model="email" type="email" suffix="@amerike.edu.mx" float-label="Correo institucional" placeholder="Coloca tu correo institucional" />
  <q-input class ="inputs" v-model="text" float-label="Nombre" placeholder="Nombre completo" />
  <q-input class ="inputs" v-model="text" float-label="Carrera que cursas" placeholder="Especifica en que carrera estás" />
  <q-btn class="inputs" color="primary" icon="mail" icon-right="send" label="Solicitar nueva contraseña"  @click="showNotification('center'),$router.push('/')" />
  <q-btn class="inputs" color="primary" label="Regresar" @click="$router.push('/')"/>
  </div>
  </q-page>
</template>

<style>
    .Imagen{
     text-align: center;
     margin: 10px;
     margin-left: auto;
     margin-right: auto;
     display: block;
     width: 20%;
     height: 5%;
  }
  .Titulos{
    font-size: 50px;
    text-align: center;
      display: block;
     margin-left: auto;
     margin-right: auto;
  }
  .contenedor{
     text-align: center;
     width: 60%;
     display: block;
    margin-left: auto;
    margin-right: auto;
     box-shadow: 0px 1px;
    border: 2px solid black;
    background-color: #EAEAEA;
  }
  .inputs{
    font-size: 20px;
    text-align: center;
    width: 70%;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding: 20px;
    margin-bottom: 40px;
  }
</style>
<script>
const alerts = [
  { color: 'blue', message: 'Revisa tu correo, se ha enviado un link de recuperación', icon: 'warning' }
]
export default {
  name: 'Contrasena',
  data () {
    return {
      visible: true,
      visible2: true
    }
  },
  methods: {
    showNotification (position) {
      const { color, textColor, icon, message, avatar } = alerts[ Math.floor(Math.random(5) * 10) % 5 ]
      this.$q.notify({
        color,
        textColor,
        icon,
        message,
        position,
        avatar,
        actions: Math.random() * 100 > 50
          ? [ { label: '', handler: () => console.log('Clicked on a notification handler') } ]
          : null,
        timeout: Math.random() * 5000 + 3000
      })
    }
  }
}
</script>

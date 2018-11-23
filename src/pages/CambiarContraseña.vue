<template>
  <q-page class="flex-center">
     <img class ="Imagen" alt="Quasar logo" src="~assets/Logo.jpg">
    <h1 class="Titulos"> Para cambiar los tu contraseña, ingresa los siguientes datos</h1>
    <div class ="contenedor">
  <q-input class="Inputs" v-model="password" stack-label="Contraseña actual" placeholder="Contraseña" type="password" float-label="Password" />
  <q-input class="Inputs" v-model="password" stack-label="Nueva contraseña" placeholder="Contraseña" type="password" float-label="Password" />
  <q-input class="Inputs" v-model="password" stack-label="Confirma nueva contraseña" placeholder="Contraseña" type="password" float-label="Password" />
  <q-btn class="inputs" color="primary" icon="mail" icon-right="send" label="Solicitar nueva contraseña"  @click="showNotification('center'),$router.push('/Principal')" />
  <q-btn class="inputs" color="primary" label="Regresar" @click="$router.push('/Principal')"/>
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
     width: 10%;
     height: 5%;
  }
  .Titulos{
    font-size: 40px;
    text-align: center;
      display: block;
     margin-left: auto;
     margin-right: auto;
  }
  .contenedor{
     text-align: center;
     width: 50%;
      height: 50%;
     display: block;
    margin-left: auto;
    margin-right: auto;
     box-shadow: 0px 1px;
    border: 2px solid black;
    background-color: #EAEAEA;
  }
    .Inputs{
        font-size: 20px;
    text-align: center;
    width: 60%;
         margin-left: auto;
    margin-right: auto;
    padding: 20px;
    margin-bottom: 40px;
        margin-top: 20px;
    }
  .inputs{
    font-size: 20px;
    text-align: center;
    width: 50%;
    display: block;
    margin-left: auto;
    margin-right: auto;
    padding: 20px;
    margin-bottom: 40px;
  }
</style>
<script>
const alerts = [
  { color: 'green', message: 'La contraseña ha sido actualizada', icon: 'tag_faces' }
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

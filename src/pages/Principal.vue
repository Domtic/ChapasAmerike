<template>
  <q-page class="flex-center">
      <q-btn class="perfil" icon="account_circle" color="primary" label="Cambiar contraseña" @click="$router.push('/EditarContrasena')"/>
      <q-card class="contenedor">
        <q-card-title>
          <p class="Titulo">Sistema de Puertas Amerike</p>
          <img class ="Imagen" alt="Logo Amerike" src="~assets/Logo.jpg">
        </q-card-title>
        <q-card-separator />
        <q-card-main>
            <div class="grid-container">
                <div class="grid-item">
                    <p class="descripcion">Salon de computo 1</p>
                    <p class="caption">--------------------</p>
                    <q-toggle readonly v-model="check1" label="Cerrado" />
                    <q-btn class="inputs" color="primary" icon-right="locked" label="Abrir Puerta"  @click="showNotification('center'),$router.push('/Principal')" />
                </div>
                <div class="grid-item">
                    <p class="descripcion">Salon de computo 2</p>
                     <p class="caption">--------------------</p>
                    <q-toggle readonly v-model="check2" label="Cerrado" />
                    <q-btn class="inputs" color="primary" icon-right="locked" label="Abrir Puerta"  @click="showNotification('center'),$router.push('/Principal')" />
                </div>
                <div class="grid-item">
                    <p class="descripcion">Taller de Videojuegos</p>
                     <p class="caption">--------------------</p>
                    <q-toggle readonly v-model="check3" label="Cerrado" />
                    <q-btn class="inputs" color="primary" icon-right="locked" label="Abrir Puerta"  @click="showNotification('center'),$router.push('/Principal')" />
                </div>
            </div>
        </q-card-main>
      </q-card>
   <q-btn class="logout" color="primary" label="Desconectarse" @click="$router.push('/')"/>
  </q-page>
</template>

<style>
    .Imagen{
        width: 100px;
        height: 100px;
        display: block;
        text-align: center;
        margin-left: auto;
        margin-right: auto;
    }
  .Titulo{
      font-size: 50px;
    text-align: center;
      display: block;
     margin-left: auto;
     margin-right: auto;
      line-height: 50px;
  }
  .contenedor{
    width: 80%;
    height: 70%;
    margin-top: 100px;
    text-align: center;
    display: block;
    margin-left: auto;
    margin-right: auto;
    background-color: #EAEAEA;
  }
  .grid-container {
  display: grid;
  grid-template-columns: auto auto auto;
  background-color: #111111;
  padding: 10px;
}
.grid-item {
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 10px;
  font-size: 30px;
  text-align: center;
}
  .descripcion{
    font-size: 20px;
  }
  .subtitulos{
        display: inline-block;
        font-size: 30px;
        margin-right: 30px;
    }
  .Switches{
     font-size: 150%;
    margin: 30px;
  }
    .logout{
    font-size: 20px;
    text-align: center;
    width: 60%;
    display: block;
    margin-left: auto;
    margin-right: auto;
    margin-top: 100px;
    padding: 20px;
    margin-bottom: 40px;
  }
    .inputs
    {
        display: block;
        text-align: center;
        margin-left: 30%;
        margin-top: 20px;
        margin-bottom: 20px
    }
    .perfil{
        text-align: right;
        margin: 0 0 0 89%;
    }
</style>

<script>
const alerts = [
  { color: 'blue', message: 'La puerta se está abriendo, un momento', icon: 'warning' }
]
export default {
  name: 'Principal',
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

<template>
  <q-page class="flex-center">
    <img class ="Imagen" alt="Quasar logo" src="~assets/Logo.jpg">
    <h1 class="Titulos"> Sistema de chapas para las puertas de Amerike
    </h1>
    <div class="Contenedor">
      <q-input class="Inputs" v-model="matricula" stack-label="Ingresa tu matricula" placeholder="Matricula"  />
      <q-input class="Inputs" v-model="password" stack-label="Ingresa tu contraseña" placeholder="Contraseña" type="password" float-label="Password" />
      <a href="#/Contrasena" class="hipervinculo" @click="$router.push('#/Contrasena')">Olvidase tu contraseña?</a>
      <q-btn class="boton" glossy color="primary" label="Ingresar"  @click="$router.push('/Principal')"/>
    </div>
  </q-page>
</template>
<style>
 body, html{
   padding: 0;
   margin: 0;
  }
   .Imagen{
     text-align: center;
     margin: 10px;
     margin-left: auto;
     margin-right: auto;
     display: block;
     width: 20%;
     height: 10%;
  }
  .Inputs{
    text-align: center;
    width: 80%;
     display: block;
     margin-left: auto;
     margin-right: auto;
    color: white;
    text-decoration: white;
  }
  .Titulos{
    font-size: 300%;
    text-align: center;
      display: block;
     margin-left: auto;
     margin-right: auto;
  }
  .boton{
    font-size: 150%;
    margin: 30px;
    text-align: center;
      display: block;
     margin-left: auto;
     margin-right: auto;
  }
  .hipervinculo{
    margin-top: 20px;
    margin-bottom: 60px;
    text-align: center;
    display: block;
     margin-left: auto;
     margin-right: auto;
    font-size: 77%;
  }
  .Contenedor{
    display: block;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    width: 40%;
    height: 40%;
    padding: 20px;
    font-size: 24px;
    border: 1px solid black;
    background-color: #EAEAEA;
    box-shadow: 0px 5px;
    border-radius: 30px;
  }
</style>

<script>
export default {
  name: 'PageIndex'
}
</script>

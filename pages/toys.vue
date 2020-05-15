<template>
  <v-row>
    <v-col cols="6">
      <question category="toy"
                en="What is your toy?"
                es="¿Cual es tu juguete?"
                aen="My toy is a car"
                aes="Mi juguete es un auto"
      >
      </question>
    </v-col>
    <v-col cols="6">
      <question category="toy"
                en="What color is it?"
                es="¿De que color es?"
                aen="It is blue and red"
                aes="Es rojo y azul"
      >
      </question>
    </v-col>
<!--  SECOND-->

    <v-col cols="6">
      <question category="toy"
                en="Why do you like it?"
                es="¿Por que te gusta?"
                aen="I like it because It is a birthday present"
                aes="Me gusta porque es un regalo de cumpleaños"
      >
      </question>

    </v-col>

    <v-col cols="6">
      <question category="toy"
                en="How often do you play with it?"
                es="¿Con que frecuencia juegas con el?"
                aen="I play with my car three times a week"
                aes="Juego con mi auto tres veces por semana"
      >
      </question>
    </v-col>


  </v-row>
</template>

<script>
    import 'material-design-icons-iconfont/dist/material-design-icons.css'
    import Question from "../components/toys/Question";
    export default {
        name: "toys",
      components: {Question}
    }
</script>

<style scoped>

</style>

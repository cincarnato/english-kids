<template>
  <v-card>
    <v-card-text>
      <v-row>
        <v-col cols="0" md="2" align-self="center" class="text-center">
          <v-avatar  size="60" left class="fixedNav">
            <img
              :src="teacher"
              alt="Teacher"

            >
          </v-avatar>
        </v-col>

        <v-col cols="12" md="10">
          <v-row>
            <v-col cols="3">
              <v-btn icon @click="playEnAudio"> <v-icon>hearing</v-icon></v-btn>
            </v-col>
            <v-col cols="9">
              <h3 class="indigo--text headline font-weight-black">{{en}}</h3>
            </v-col>

            <v-col cols="3">
              <v-btn icon @click="playEsAudio"> <v-icon>hearing</v-icon></v-btn>
            </v-col>
            <v-col cols="9">
              <h3 class="grey--text title">{{es}}</h3>
            </v-col>
          </v-row>
        </v-col>

        <v-divider></v-divider>
        <v-col cols="0" md="2" align-self="center" class="text-center">
          <v-avatar  size="60" left class="fixedNav">
            <img
              :src="student"
              alt="Teacher"

            >
          </v-avatar>
        </v-col>


        <v-col cols="12" md="10">
          <v-row>
            <v-col cols="3">
              <v-btn icon @click="playAnswerEnAudio"> <v-icon>volume_up</v-icon></v-btn>
            </v-col>
            <v-col cols="9">
              <h3 class="deep-orange--text headline font-weight-black">{{aen}}</h3>
            </v-col>

            <v-col cols="3">
              <v-btn icon @click="playAnswerEsAudio"> <v-icon>volume_up</v-icon></v-btn>
            </v-col>
            <v-col cols="9">
              <h3 class="grey--text title">{{aes}}</h3>
            </v-col>
          </v-row>
        </v-col>




      </v-row>
    </v-card-text>

  </v-card>
</template>

<script>
  export default {
    name: "Question",
    props: {
      teacher: {type: String, default: 'teacher.png'},
      student: {type: String, default: 'tux.png'},
      category: String,
      en: String,
      es: String,
      aen: String,
      aes: String
    },
    computed:{
      getEnAudioFilename(){
        let sound = this.en.toLowerCase().replace('?','').split(' ').join('-')
        return '/'+this.category+'/'+sound+'.mp3'
      },
      getEsAudioFilename(){
        let sound = this.es.toLowerCase().replace(/¿|\?/g,'').split(' ').join('-')
        return '/'+this.category+'/'+sound+'.mp3'
      },
      getAnswerEnAudioFilename(){
        let sound = this.aen.toLowerCase().replace(/ñ/g,'n').split(' ').join('-')
        return '/'+this.category+'/'+sound+'.mp3'
      },
      getAnswerEsAudioFilename(){
        let sound = this.aes.toLowerCase().replace(/ñ/g,'n').split(' ').join('-')
        return '/'+this.category+'/'+sound+'.mp3'
      },
    },
    methods:{
      playEnAudio(){
        let audio = new Audio(this.getEnAudioFilename);
        audio.play();
      },
      playEsAudio(){
        let audio = new Audio(this.getEsAudioFilename);
        audio.play();
      },
      playAnswerEnAudio(){
        let audio = new Audio(this.getAnswerEnAudioFilename);
        audio.play();
      },
      playAnswerEsAudio(){
        let audio = new Audio(this.getAnswerEsAudioFilename);
        audio.play();
      }
    }
  }
</script>

<style scoped>

</style>

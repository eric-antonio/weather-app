<template>
  <q-page class="flex column" id="q-page1">


    <div class="col" q-pt-lg q-px-md>

      <q-input
        class="input01"
        v-model="search"
        placeholder="Search"
        borderless
        dark>

        <template v-slot:before>
          <q-icon
            @click="getLocation"
            name="my_location" />
        </template>

        <template v-slot:append >
          <q-btn round dense flat icon="search" />
        </template>
      </q-input>
    </div>

    <template v-if="weatherDate">
      <div class="col text-white text-center">
      <div class="text-h4 text-weigth-light">
        Maputo
      </div>
      <div class="text-h6 text-weigth-light">Sol</div>
      <div class="text-h1 text-weight-thin q-my-lg relative-position">
        <span>23</span>
        <span class="text-h4 relative-position   degree">℃</span>
      </div>
      </div>

      <div class="col text-center">
      <img src="https://www.fillmurray.com/100/100" alt="Bill">
      </div>
    </template>

    <template v-else>
      <div class="col column text-center text-white">
        <div class="col text-h2 text-weigth-thin">
          Quasar <br> Weather!
          <p id="descrição">Desenvolvido por @eric-antonio</p>
        </div>
        <q-btn class="col" flat @click="getLocation">
          <q-icon left size="2em" name="my_location" />
          <div>FIND MY LOCATION</div>
        </q-btn>
      </div>

    </template>


    <div class="skyline">

    </div>



  </q-page>
</template>

<!-- Script -->
<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    return{
      search:'',
      weatherDate:null,
      lat:null,
      lon:null,
      apiUrl:'https://api.openweathermap.org/data/2.5/weather',
      apiKey:'c3e6d49156458cb27f9f08065e140e13',
    }
  },
  methods:{
    getLocation(){
      navigator.geolocation.getCurrentPosition(position =>{
        console.log('position:',position)
        this.lat= position.coords.latitude
        this.lon= position.coords.longitude
        this.getWeatherByCoords()
      })
    },getWeatherByCoords(){
      this.$aios(`${ this.apiUrl }?lat=${this.lat }&lon=${this.lon}&appid=${this.apiKey}`)
    }
  }
})
</script>
<!-- Style -->

<style lang="sass">
  #q-page1
    padding-top: 10px
    background: linear-gradient(to bottom, #267871, #136a8a)

  .input01
    margin:0px 10px 0px 10px
  .degree
    top: -42px


</style>

<style>
  .skyline{
    flex: 0 0 100px;
    background:url(../img/townsilhouette2.png );
    background-size:contain;
    background-repeat: no-repeat;
    background-position: center bottom
  }
  #descrição{
    text-align: center;
    font-size: 16px;
  }

</style>

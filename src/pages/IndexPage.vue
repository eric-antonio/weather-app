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
          <q-icon name="my_location" />
        </template>

        <template v-slot:append >
          <q-btn round dense flat icon="search" />
        </template>
      </q-input>
    </div>

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

    <div class="col skuline">
      
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
      search:''
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

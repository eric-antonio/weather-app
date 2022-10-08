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

  </q-page>
</template>

<!-- Script -->
<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  data(){
    
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




</style>

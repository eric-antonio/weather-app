<template>
  <q-page class="flex column" id="q-page1">


    <div class="col" q-pt-lg q-px-md>

      <q-input
        class="input01"
        v-model="text"
        placeholder="Search"
        borderless
        dark>

        <template v-slot:before>
          <q-icon name="event" />
        </template>

        <template v-slot:hint>
          Field hint
        </template>

        <template v-slot:append>
          <q-btn round dense flat icon="add" />
        </template>
      </q-input>
    </div>

  </q-page>
</template>

<!-- Script -->
<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>

<!-- Style -->

<style lang="sass">
  #q-page1
    padding-top: 10px
    background: linear-gradient(to bottom, #267871, #136a8a)

  .input01
    margin-left:10px


</style>

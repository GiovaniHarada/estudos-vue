<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <side-bar/>
    </div>
    <div class="column is-three-quarter">
      <time-form/>
      
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';
import TimeForm from './components/Formulario.vue';


export default defineComponent({
  components: { SideBar, TimeForm },
  name: 'App'
});
</script>

<style>

</style>

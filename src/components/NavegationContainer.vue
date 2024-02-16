<script lang="ts">

import { defineComponent } from 'vue'
import AppButtom from './AppButtom.vue';
import AppCurrentIndexCircle from './AppCurrentIndexCircle.vue';

export default defineComponent({
  setup() {
  },
  components: { AppButtom, AppCurrentIndexCircle }
})

</script>
 
 ««««««««««««««««««««--Template--»»»»»»»»»»»»»»»»»»»»»

<template>
  <div class="container__navegation-bar">
    <AppButtom />
    <AppCurrentIndexCircle />
  </div>
</template>

 
 ««««««««««««««««««««--Style--»»»»»»»»»»»»»»»»»»»»»

<style></style>


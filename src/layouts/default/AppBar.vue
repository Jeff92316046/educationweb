<template>
  <v-navigation-drawer
    v-model="drawer"
    temporary
    color="blue-lighten-4"
  >
      <v-btn href="/" class="d-block my-2 pa-2 mt-md-10  mt-sm-10 mt-16 w-75 mx-8"  color="blue-lighten-5"> 首頁</v-btn>
      <v-btn href="/teach" class="d-block my-2 pa-2 w-75 mx-8" color="blue-lighten-5">教學</v-btn>
      <v-btn href="/test" class="d-block my-2 pa-2 w-75 mx-8" color="blue-lighten-5">測驗</v-btn>
  </v-navigation-drawer>
  <v-app-bar :elevation="10" flat color="primary" class="" v-if="width<=960" >
    <v-app-bar-title >
      <v-btn class="pa-0 ma-0 " @click.stop="drawer = !drawer" >
          <v-icon icon="mdi-format-list-bulleted" />
      </v-btn>
    </v-app-bar-title>
  </v-app-bar>
  <v-app-bar :elevation="10" max-width="960px" rounded="4" color="primary"  v-if="width>960" >
    <v-app-bar-title   >
      <v-btn class="pa-0 ma-0 " href="/" >
          <v-icon icon="mdi-home" />
      </v-btn>
      <v-btn class="pa-0 ma-0 " href="/teach" >
          教學
      </v-btn> 
      <v-btn class="pa-0 ma-0 " href="/test">
          測驗
      </v-btn>
    </v-app-bar-title>
  </v-app-bar>
</template>

<script setup>
  import { useWindowSize } from '@vueuse/core'
  import { ref  } from 'vue'
  const { width, height } = useWindowSize()
  const drawer = ref(null)
</script>




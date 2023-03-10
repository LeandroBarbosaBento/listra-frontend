<template>
  <v-app id="inspire">
    <v-app-bar
      color="#7D28F7"
      :elevation="0"
    >
      <div class="d-flex justify-center align-center w-100">
        <v-img
          height="45"
          :src="ListrasLogo"
        ></v-img>
      </div>
    </v-app-bar>

    <v-main class="main-class">
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
import ListrasLogo from '@/assets/img/LISTRA_branco_verde.png';
  export default {
    data: () => ({
      ListrasLogo: ListrasLogo,
    }),
  }
</script>
<style scoped>
.main-class{
  background-color: #EBEEF2;
}
</style>

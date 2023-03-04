<template>
  <v-app id="inspire">
    <v-navigation-drawer
        permanent
        v-model="drawer"
      >
        <template v-slot:prepend>
          <v-list-item
            lines="two"
            title="Listras"
            subtitle="Feito por Leandro Barbosa"
          ></v-list-item>
          <!-- prepend-avatar="https://randomuser.me/api/portraits/women/81.jpg" -->
        </template>

        <v-divider></v-divider>

        <v-list density="compact" nav>
          <v-list-item
            v-for="item in menu"
            :key="item.name"
            :prepend-icon="item.icon"
            :title="item.name"
            :to="item.to"
          ></v-list-item>
        </v-list>
      </v-navigation-drawer>

    <v-app-bar
      color="#7D28F7"

    >
      <v-app-bar-nav-icon color="white" @click="drawer = !drawer"></v-app-bar-nav-icon>

      <div class="d-flex justify-center align-center w-100">
        <v-img
          height="37"
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
      drawer: false,
      ListrasLogo: ListrasLogo,
      menu: [
        {name: 'Simulação de Financiamento', to: '/', icon:'mdi-home-city'},
        {name: 'Cadastrar carro', to: '/add-car', icon:'mdi-account'}
      ]
    }),
  }
</script>
<style scoped>
.main-class{
  background-color: #F5F5F5;
}
</style>

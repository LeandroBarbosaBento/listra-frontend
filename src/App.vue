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
          <v-list-item prepend-icon="mdi-home-city" title="Home" value="home"></v-list-item>
          <v-list-item prepend-icon="mdi-account" title="My Account" value="account"></v-list-item>
          <v-list-item prepend-icon="mdi-account-group-outline" title="Users" value="users"></v-list-item>
        </v-list>
      </v-navigation-drawer>

    <v-app-bar>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <div class="d-flex justify-center align-center w-100">
        <h1>Título listras</h1>
      </div>
    </v-app-bar>

    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
  export default {
    data: () => ({ drawer: null }),
  }
</script>

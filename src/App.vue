<template>
  <v-app>
    <v-app-bar
      app
      color="blue"
      :elevation="2"
    >
    
      <v-app-bar-title>
        <router-link class="text-decoration-none text-white" to="/">
          <h3 class="text-h4">TManage</h3>
        </router-link>
      </v-app-bar-title>

      <div class="d-flex ga-3 mr-10">
        <router-link to="/" class="text-h5 text-decoration-none text-white">Главная</router-link>
        <router-link to="/tasks" class="text-h5 text-decoration-none text-white">Задачи</router-link>
      </div>

    </v-app-bar>
    <v-main>

      <router-view>
        
      </router-view>

    </v-main>
     
   </v-app>
</template>

<script>
export default {
  name: 'App'
}
</script>


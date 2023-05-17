<template>
  <v-card>
    <v-layout>
      <v-navigation-drawer v-model="drawer" :rail="rail" permanent @click="rail = false">
        <v-list-item prepend-avatar="https://randomuser.me/api/portraits/men/85.jpg" title="John Leider" nav>
          <template v-slot:append>
            <v-btn variant="text" icon="mdi-chevron-left" @click.stop="rail = !rail"></v-btn>
          </template>
        </v-list-item>
        <v-divider></v-divider>
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-home" title="Home" value="home"></v-list-item>
          <v-list-item prepend-icon="mdi-text-box-multiple-outline" title="Documents" value="documents"></v-list-item>
          <v-list-item prepend-icon="mdi-calendar-month" title="Calendar" value="calendar"></v-list-item>
          <v-list-item prepend-icon="mdi-folder-account" title="Projects" value="projects"></v-list-item>
        </v-list>
      </v-navigation-drawer>
      <v-app-bar title="Home"></v-app-bar>
      <!-- <v-app-bar color="grey-lighten-2" flat location="bottom"></v-app-bar> -->
      <v-main>
        <v-container>
          <CardTest></CardTest>
        </v-container>
      </v-main>
    </v-layout>
  </v-card>
</template>

<script>
import CardTest from './components/CardTest.vue'
export default {
  name: 'App',
  components: {
    CardTest
  },
  data() {
    return {
      drawer: true,
      items: [
        { title: 'Home', icon: 'mdi-home' },
        { title: 'Documents', icon: 'mdi-text-box-multiple-outline' },
        { title: 'Calendar', icon: 'mdi-calendar-month' },
        { title: 'Projects', icon: 'mdi-folder-account' },
      ],
      rail: true,
    }
  },
}
</script>
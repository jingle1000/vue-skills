<template>
  <v-app>
    <Nav />
    <Menu />
    <v-content>
      <v-container>
  <Skills/>
      </v-container>
    
    </v-content>
  </v-app>
</template>

<script>
import Menu from './components/Menu'
import Skills from './components/Skills'

export default {
  name: 'App',
  components: {
    Menu,
    Skills
  },
  data () {
    return {
      //
    }
  }
}
</script>
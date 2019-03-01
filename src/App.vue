<template>
  <v-app>
    <Nav />
    <Menu />
    <v-content>
      <v-container>
        <Skills :skillArray="skills" @add-skill="addSkill($event)"></Skills>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import Menu from './components/Menu'
  import Skills from './components/Skills'
  import {EventBus} from './eventbus.js'
  export default {
    name: 'App',
    components: {
      Menu,
      Skills
    },
    data() {
      return {
        maxSkills: 10,
        skills: ["Skill Placeholder", "test"],
        toDel: 0
      }
    },
    methods: {
      addSkill(skill) {
        this.skills.push(skill);
      },
    },
    mounted() {
      EventBus.$on('delete-skill', (s) => {
        console.log(this.skills.indexOf(s));
        this.skills.pop();
      });
    }
  }
</script>
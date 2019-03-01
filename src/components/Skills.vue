<template>
  <div class="hello">
    <v-card-text>
      <h1 class="text-xs-center">Add a Skill</h1>
    </v-card-text>
    <v-card class="pa-4 mb-3 elevation-6">
      <v-layout column wrap justify-center class="ma-1">
      <v-flex md12>
        <form action="#">
          <v-text-field name="name" id="id" placeholder="Book Title..." v-model="skill"></v-text-field>
        </form>
      </v-flex>
      <v-flex md12>
        <v-btn block class="mt-3 mb-1" color="info" @click="addSkill()">Add Skill</v-btn>
      </v-flex>
    </v-layout>
    </v-card>
    <Skill class="pa-3 ma-4 elevation-6" v-for="(skill, index) in skillArray" :key="index">
      <p>{{ skill }}</p>
    </Skill>
  </div>
</template>

<script>
import Skill from './Skill'

  export default {
    name: 'Skills',
    components: {
      Skill
    },
    props: {
      skillArray: Array
    },
    data() {
      return {
        skill: '',
      }
    },
    methods: {
      addSkill() {
        this.$emit("add-skill", this.skill);
      }
    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    padding: 3px;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
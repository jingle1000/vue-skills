<template>
  <div class="hello">
    <h1 class="display">Search for a Book</h1>
    <form action="#">
      <v-text-field name="name" label="label" id="id"></v-text-field>
  </form>
  <ul>
    <li v-for="(item, index) in skills" :key="index">{{ item.skill }}</li>
  </ul>
  </div>
</template>

<script>
  export default {
    name: 'Skills',
    data() {
      return {
        skills: [{
            "skill": "Vue.js"
          },
          {
            "skill": "Python"
          },
          {
            "skill": "Computer Science"
          }
        ]
      }
    },
    props: {
      msg: String
    }
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
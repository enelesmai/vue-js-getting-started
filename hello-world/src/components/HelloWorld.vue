<template>
  <div class="hello container">
    <h1>{{ msg }}</h1> 
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'HelloWorld',
  data() {
    return {
      users: null,
    };
  },
  props: {
    msg: String
  },
  created: function() {
    axios
      .get('https://jsonplaceholder.typicode.com/users')
      .then(res => {
        this.users = res.data;
      })
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
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

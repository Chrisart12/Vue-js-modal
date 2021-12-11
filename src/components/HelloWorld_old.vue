<template>
<h3>{{ title }}</h3>
  <div class="hello">
    Je suis ici
  </div>
  <input type="text" ref="lastname">
  <button @click="handleClick">Cliquer ici</button>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      title: 'My First Vue app :)'
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.lastname)
      this.$refs.lastname.classList.add("active")
      this.$refs.lastname.focus()
    }
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

.active {
  background: #42b983;
}
</style>

<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr />
    <pre>[{{ now }}]</pre>
    <router-link to="/other">Go To Other</router-link>
  </section>
</template>

<script>
export default {
  data() {
    return {
      title: 'おしりの日常',
      message: 'this is message.',
      now: 'wait....'
    }
  },
  created() {
    setInterval(() => {
      const d = new Date()
      this.now = d.getHours() + ':' + d.getMinutes() + ':' + d.getSeconds()
    }, 1000)
  }
}
</script>

<style>
.container {
  padding: 5px 10px;
}
h1 {
  font-size: 60pt;
}
p {
  padding-top: 5px;
  font-size: 20pt;
}
pre {
  padding: 10pt;
  font-size: 10pt;
  background: #beff0d;
}
hr {
  margin: 10pt 5pt;
}
</style>

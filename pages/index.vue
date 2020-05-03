<template>
  <section class="container">
    {{ data }}<br />
    {{ title }}<br />
    {{ now }}<br />
    <router-link to="/other">Go To Other</router-link>
  </section>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const response = await $axios.$get(
      'https://5380qow063.execute-api.ap-northeast-1.amazonaws.com/demo'
    )
    return {
      data: response
    }
  },
  data() {
    return {
      title: 'おしりの日常' + '\u3000' + 'サイドストーリ' + '\u3000' + '修正２',
      // message: 'this is message.',
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

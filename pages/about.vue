<template>
  <div class="container">
    <div>
      {{ip}}
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      ip: null
    }
  },
  methods: {
    async fetchSomething () {
      const ip = await this.$axios.$get('http://luckyfiftythree.co.uk/admin/api/collections/get/projects?token=b5f2f0beacea5dd2af67f766a11ad4')
      this.ip = ip
    }
  },
  mounted () {
    this.fetchSomething()
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

svg {
  width:100%;
  max-width:800px;
  height:auto;
}
</style>

<template>
  <div id="app-container">
    <Layout>
      <template v-slot:left>
         <SiteAside></SiteAside>
      </template>

      <div class="main">
        <RouterView></RouterView>
      </div>

      <template v-slot:right>
        <div class="right">
          right
        </div>
      </template>

    </Layout>
    

  </div>
</template>

<script>

import Layout from './components/Layout'
import SiteAside from './components/SiteAside'

// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  components: {
    Layout,
    SiteAside
  },
  data: () => {
    return {
    }
  },
  methods: {
    
  }
}
</script>

<style scoped>
#app-container {
  /* text-align: center; */
 /* color: #2c3e50; */
  /* width: 500px; */
  height: 600px;
  position: relative;
  /* background: #2c3e50; */
}


</style>

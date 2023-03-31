<template>
  <header>
    <NavBar/>
  </header>
  <ContentComp
  showButton='true'/>
  <FooterComp/>
</template>

<script>
import NavBar from './components/NavBar.vue'
import FooterComp from './components/FooterComp.vue'
import ContentComp from './components/ContentComp.vue'

export default {
    name: 'App',
    components: {
      NavBar,
      ContentComp,
      FooterComp
    },
    methods: {

    }
}
</script>


<style scoped>
  
</style>

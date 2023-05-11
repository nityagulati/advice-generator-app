<template>
  <ContentCard></ContentCard>
  <Footer></Footer>
</template>

<script>
import ContentCard from './components/ContentCard.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    ContentCard,
    Footer
  }
}
</script>

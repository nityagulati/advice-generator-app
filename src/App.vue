<template>
  <ContentCard role="main"></ContentCard>
  <Footer role="footer"></Footer>
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

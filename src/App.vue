<template>
  <div class="justify-between flex flex-col h-screen">
    <div class="">
      <Header />
      <router-view/>
    </div>
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
}
</script>
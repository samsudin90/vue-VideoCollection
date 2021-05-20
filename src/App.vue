<template>
  <div class="">
    <Header />
  </div>
  <router-view/>
</template>

<script>
import Header from '@/components/Header'

export default {
  name: 'App',
  components: {
    Header
  }
}
</script>
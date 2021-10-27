<template>
  <div class="home">
    <TheHeader />
    <MainBody />
  </div>
</template>

<script>
// @ is an alias to /src
import MainBody from '@/components/MainBody.vue'
import TheHeader from '@/components/TheHeader.vue'

export default {
  name: 'Home',
  components: {
    TheHeader,
    MainBody,
  }
}
</script>

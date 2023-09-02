<template>
  <div class="home">
    <BaseHeader />
    <LandingView />
    <BaseFAQ />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
  import BaseHeader from '@/components/BaseHeader.vue'
  import BaseFAQ from '@/components/BaseFAQ.vue'
  import LandingView from '@/components/LandingView.vue'

export default {
  name: 'HomeView',
  components: {
    // HelloWorld,
    BaseHeader,
    BaseFAQ,
    LandingView
  }
}
</script>

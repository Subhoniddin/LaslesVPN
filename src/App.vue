<template lang="">
  <div class="container mx-auto">
     <app-bar/>
     <home-page/>
     <restagle-page/> 
     <fitures-page/> 
     <sale-page/>
     <map-page/>
     <pricing-page/>
     <subscribe-page/>
     <footer-page/>
  </div>
</template>
<script>
import AppBar from '@/components/AppBar.vue'
import HomePage from '@/components/HomePage.vue'
import RestaglePage from '@/components/RestanglePage.vue'
import FituresPage from '@/components/FituresPage.vue'
import SalePage from '@/components/SalePage.vue';
import MapPage from '@/components/MapPage.vue';
import PricingPage from '@/components/PricingPage.vue'
import SubscribePage from '@/components/SubscribePage.vue'
import FooterPage from '@/components/FooterPage.vue'

export default {
  components: {
    AppBar,
    HomePage,
    RestaglePage,
    FituresPage,
    SalePage,
    MapPage,
    PricingPage,
    SubscribePage,
    FooterPage
  },
}
</script>
<style lang=""></style>

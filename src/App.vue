<template>
  <div class="flex container h-screen w-full mx-auto ">
    <navbar/>
    <tweet/>
    <trend/>
    
  </div>
  

  
</template>

<script>
import navbar from './components/navbar.vue'
import Trend from './components/trend.vue'
import trendVue from './components/trend.vue'
import Tweet from './components/tweet.vue'


export default {
  name:'App',
  components:{
    navbar,
    Tweet,
    Trend
  }

}
</script>

<style>

</style>
<template>
    <div class="w-1/3 h-full border-l border-lighter py-2 px-6 overflow-y-scroll relative"> 
        <input class="rounded-full bg-lighter w-full p-2 pl-11 outline-none text-sm" placeholder="Search Twitter">
        <img class="absolute left-0 top-0 w-5 h-5 mt-4 ml-11" src="../assets/search.png">
        <div class="w-full bg-lightest rounded-lg ">
            <div class="flex justify-between items-center p-3 mt-2">
                <p class="text-lg font-bold">Trends for you</p>
                <img class="w-5 h-5" src="../assets/cog.png">
            </div>
            <button v-for="trend in trending" class="w-full flex justify-between border-t border-lighter hover:bg-lighter p-3">
                <div>
                    <p class="text-sm text-left leading-tight text-dark">{{trend.top}}</p>
                    <p class="font-bold text-left leading-tight">{{trend.title}}</p>
                    <p class=" text-left leading-tight text-dark">{{trend.bottom}}</p>
                </div>
            </button>
            <button class="text-blue p-3 w-full text-left hover:bg-lighter border-t border-lighter"> 
                Show more
            </button>
        </div>
        <div class="w-full bg-lightest rounded-lg ">
            <div class="p-3 mt-2">
                <p class="text-lg font-bold">Who to Follow</p>
            </div>
            <card/>
            <button class="p-3 w-full hover:bg-lighter text-left text-blue border-t border-lighter">
            Show More
            </button>
            
        </div>

    </div>
  
</template>

<script>
import card from './card.vue'


export default {
  components: { card },
    name:'trend',
    data(){
        return{
        trending: [
        {top: 'Trending in TX', title: 'Gigi', bottom: 'Trending with: Rip Gigi'},
        {top: 'Music', title: 'We Won', bottom: '135K Tweets'},
        {top: 'Pop', title: 'Blue Ivy', bottom: '40k tweets'},
        {top: 'Trending in US', title: 'Denim Day', bottom: '40k tweets'},
        {top: 'Trending', title: 'When Beyonce', bottom: '25.4k tweets'},
      ]
        }
    }

}
</script>

<style>

</style>
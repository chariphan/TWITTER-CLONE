<template>
  <div class="lg:w-1/5 border-r border-lighter lg:px-6 py-2 flex flex-col justify-between">
    <!--ส่วนบนที่1-->
    <div> 
        <div class="h-12 w-12">
           <img class="ml-7" src="../assets/logo.png" />
        </div>
        <div> 
           <button v-for="tab in tabs" class="flex items-center py-2 px-4 mr-auto mb-3 rounded-full hover:text-blue cursor-pointer">
              
              <p class="text-lg font-semibold text-left hidden lg:block">{{tab.title }}</p>
           </button>
        </div>
        <button class="bg-blue text-white rounded-full w-12 h-12 lg:h-auto lg:w-full p-3 font-semibold focus:outline-none hover:bg-darkblue">
          <p class="hidden lg:block">Tweet</p>
          <p class="lg:hidden  ">+</p>
        </button>
    </div>

    <!--ส่วนล่างที่2-->
    <div class="lg:w-full relative"> 
        <button @click="dropdown=true" class="flex item-center w-full hover:bg-lightblue rounded-full p-2 focus:outline-none">
            <img class="w-10 h-10 rounded-full border border-lighter" src="../assets/profile.jpg">
            <div class="hidden lg:block ml-4 p-1"> 
                <p class="text-sm font-bold leading-tight">Steph Dietz</p>
                <p class="text-sm font-bold leading-tight text-gray-600">@calalamm</p>
            </div>
            <img class="hidden lg:block w-4 h-5 ml-auto pt-3" src="../assets/arrow.png">
        </button>
        <!--ตัวโชว์-->
        <div v-if="dropdown===true" class="absolute bottom-0 left-0 w-64 bg-white rounded-lg shadow-md border-lightest mb-16">
            <button @click="dropdown=false" class="p-3 flex item-center w-full hover:bg-lightest   focus:outline-none">
               <img class="w-10 h-10 rounded-full border border-lighter" src="../assets/profile.jpg">
               <div class="ml-4 p-1"> 
                   <p class="text-sm font-bold leading-tight">Steph Dietz</p>
                   <p class="text-sm font-bold leading-tight text-gray-600">@calalamm</p>
               </div>
               <img class="w-4 h-5 ml-auto pt-3 text-blue" src="../assets/check.png">
            </button>
            <button @click="dropdown=false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm">
              Add an existing account 
            </button>
            <button @click="dropdown=false" class="w-full text-left hover:bg-lightest border-t border-lighter p-3 text-sm">
              Log out@calalamm
            </button>

        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  methods: {},
  data() {
    return {
      tabs: [
        { title: 'Home', id:'home'},
        {title: 'Explore', id: 'explore'},
        { title: 'Notifications', id: 'notifications'},
        { title: 'Messages', id: 'messages'},
        { title: 'Bookmarks', id: 'bookmarks'},
        { title: 'Lists', id: 'lists'},
        { title: 'Profile', id: 'profile'},
        { title: 'More', id: 'more'}
        
      ],
      dropdown:false
    };
  },
};
</script>

<style>
</style>
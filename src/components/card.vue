<template>
   <button v-for="friend in friends" class="w-full flex hover:bg-lighter p-3 border-t border-lighter">
          <img :src="`${friend.src }`" class="w-12 h-12 rounded-full border border-lighter" />
          <div class="hidden lg:block ml-4">
            <p class="text-sm font-bold leading-tight"> {{ friend.name }} </p>
            <p class="text-sm leading-tight"> {{ friend.handle }} </p>
          </div>
          <button class="ml-auto text-sm text-blue py-1 px-4 rounded-full border-2 border-blue">
            Follow
          </button>
    </button>
</template>

<script>
export default {
    name:'card',
    data(){
        return{
        friends: [
        {src: 'cat.jpg', name: 'Elon Musk', handle: '@teslaBoy'},
        {src: 'dog1.jpg', name: 'Adrian Monk', handle: '@detective:)'},
        {src: 'dog2.jpg', name: 'Kevin Hart', handle: '@miniRock'}
      ]
        }
    }

}
</script>

<style>

</style>
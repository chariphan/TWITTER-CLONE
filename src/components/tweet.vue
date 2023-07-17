<template>
    <div class="w-1/2 h-full overflow-y-scroll"> 
        <div class="px-5 py-3 border-b border-lighter flex items-center justify-between"> 
            <h1 class="text-xl font-bold">Home</h1>
            <img class="w-6 h-6" src="../assets/star.png">
        </div>
        <div class="px-5 py-3 border-b-8 border-lighter flex">
            <div>
                <img class="w-12 h-12 rounded-full" src="../assets/profile.jpg">
            </div>

            <form v-on:submit.prevent="addNewTweet" class="w-full px-4 relative ">
                <textarea v-model="tweet.content" class="w-full outline-none mt-3" placeholder="what's up?"></textarea>
                <div class="flex items-center">
                    <img class="w-4 h-4 mr-4" src="../assets/image.png">
                    <img class="w-4 h-4 mr-4" src="../assets/film.png">
                    <img class="w-4 h-4 mr-4" src="../assets/bar.png">
                    <img class="w-4 h-4 mr-4" src="../assets/smile.png">
                </div>
                <button type="submit" class="h-10 px-4 text-white font-semibold bg-blue hover:bg-darkblue rounded-full absolute bottom-0 right-0">Tweet</button>
            </form>
        </div>
        <!--test-->
        <div class="flex flex-col-reverse">
        <div v-for="tweet in tweets" class="w-full p-4 border-b hover:bg-lighter flex">
            <div class="flex-none mr-4 ">
                <img src="../assets/profile.jpg" class="h-12 w-12 rounded-full flex-none">
            </div>            
            <div class="w-full"> 
                <div class="flex item-center w-full">
                    <p class="font-semibold">Steph Dietz</p>
                    <p class=" text-dark ml-2 text-sm pt-1">@calalamm</p>
                    <p class=" text-dark ml-2 text-sm pt-1">1 minute</p>
                </div>
                <p class="py-2">{{ tweet.content }}</p>
                <div class="flex items-center justify-between w-full">
                    <!--1-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="chat.png">
                        <p></p>
                    </div>
                    <!--2-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="retweet.png">
                        <p></p>
                    </div>
                    <!--3-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="heart.png">
                        <p></p>
                    </div>
                    <!--4-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="share.png">
                        <p></p>
                    </div>
                </div>

                
            </div>
            
        </div>
        </div>


        
        <!--test/-->
        <div v-for="follow in following" class="w-full p-4 border-b hover:bg-lighter flex">
            <div class="flex-none mr-4 ">
                <img :src="`${follow.src}`" class="h-12 w-12 rounded-full flex-none">
            </div>
            <div class="w-full"> 
                <div class="flex item-center w-full">
                    <p class="font-semibold">{{follow.name}}</p>
                    <p class=" text-dark ml-2 text-sm pt-1">{{follow.handle}}</p>
                    <p class=" text-dark ml-2 text-sm pt-1">{{follow.time}}</p>
                </div>

                <p class="py-2">{{ follow.tweet }}</p>

                <div class="flex items-center justify-between w-full">
                    <!--1-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="chat.png">
                        <p>{{ follow.comments }}</p>
                    </div>
                    <!--2-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="retweet.png">
                        <p>{{ follow.comments }}</p>
                    </div>
                    <!--3-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="heart.png">
                        <p>{{ follow.comments }}</p>
                    </div>
                    <!--4-->
                    <div class="flex items-center text-sm text-dark">
                        <img class="mr-3 w-4 h-4" src="share.png">
                        <p>{{ follow.comments }}</p>
                    </div>
                </div>
            </div>

        </div>

    </div>
  
</template>

<script>
export default {
    name:'Tweet',
    data(){
        return{
        following: [
        {src: 'cat.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '20 min', tweet: 'Should I just quarantine on mars??', comments: '1,000', retweets: '550', like: '1,000,003'},
        {src: 'dog2.jpg', name: 'Kevin Hart', handle: '@miniRock', time: '55 min', tweet: 'Should me and the rock do another sub-par movie together????', comments: '2,030', retweets: '50', like: '20,003'},
        {src: 'cat.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Haha just made a flame thrower. Shld I sell them?', comments: '100,000', retweets: '1,000,002', like: '5,000,003'},
        {src: 'cat.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Just did something crazyyyyyyy', comments: '100,500', retweets: '1,000,032', like: '5,000,103'}
        ],
        tweets: [{content: 'It is so nice outside!'}],
        tweet: {content: ''}
        }
    },
    methods:{
        addNewTweet(){
            let newTweet={
                content:this.tweet.content
            };
            this.tweets.push(newTweet)
        }
    }

}
</script>

<style>

</style>
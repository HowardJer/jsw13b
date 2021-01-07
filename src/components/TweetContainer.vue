<template>
    <div>
        <vue-tweets @tweetContent='handleChildUpdate'/>
        <button id="grid-or-list" @click="toggleView">toggle view</button>
        <div id="tweets" :class="{ 'list-view': listView }">
            <article class="tweet" v-for="(tweet, index) in tweets" :key="index">
                <h3>{{ tweet.author }}</h3>
                <h5>{{ tweet.date }}</h5>
                <p>{{ tweet.text }}</p>
            </article>
        </div>
    </div>
</template>

<script>
    import VueTweets from './Tweets.vue';
    
    export default {
        name: "vue-tweet-container",
        components: {
            VueTweets
        },
        data() {
            return {
                listView: false,
                tweets: []
            }
        },
        methods: {
            handleChildUpdate: function(data) {
                this.tweets = data;
            },
            toggleView() {
                this.listView = !this.listView;
                if(this.listView == true) {
                    document.getElementById('grid-or-list').innerText = 'view as a grid';
                }else{
                    document.getElementById('grid-or-list').innerText = 'view as a list';
                }
            }
        }
    }
</script>

<style scoped>
    #grid-or-list {
        display: none;
    }
    #tweets {
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
        padding: 1rem;
    }
    .tweet {
        background-color: skyblue;
    }
    @media only screen and (min-width: 600px) {
        #grid-or-list {
            display: inline;
        }
        #tweets {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 1rem;
            padding: 1rem;           
        }
        .tweet {
            border: 2px solid black;
        }
        #tweets.list-view {
            grid-template-columns: 1fr;
        }
    }
</style>
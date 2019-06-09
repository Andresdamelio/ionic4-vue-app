<template>
    <div>
        <ion-card v-for="post in posts" :key="post.data.id">
            <ion-card-content>
                <ion-label>{{ post.data.title }}</ion-label>
            </ion-card-content>
        </ion-card>
    </div>
</template>

<script>

import axios from 'axios';
export default {
    data() {
        return {
            posts: [],
        }
    },
    methods: {
        async loadPost(){
            const response = await axios.get('https://www.reddit.com/r/sports.json');
            this.posts = response.data.data.children;
            console.log(this.posts);
        }
    },

    mounted(){
        this.loadPost();
    }
}
</script>

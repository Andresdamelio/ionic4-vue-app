<template>
    <div>
        <ion-card v-for="post in posts" :key="post.data.id" style="border: 1px solid #fff; padding: 10px; margin-bottom:2px;" mode="md">
            <ion-card-title color="dark">
                {{ post.data.title }}
            </ion-card-title>
            <ion-card-subtitle color="dark">
                Posted by {{ post.data.author }}
            </ion-card-subtitle>
            <ion-card-content mode="md">
                <template v-if="post.data.thumbnail.startsWith('https://')">
                    <img :src="post.data.thumbnail" alt="">
                </template>
            </ion-card-content>
            <ion-button color="primary" expand="full" @click="viewMore">
                View more
            </ion-button>
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
        },

        viewMore(){
            alert('hola parroquia')
        }
    },

    mounted(){
        this.loadPost();
    }
}
</script>

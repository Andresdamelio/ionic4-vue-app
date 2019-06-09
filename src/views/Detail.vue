<template>
    <ion-card>
        <ion-card-header>
            <ion-card-title>
                {{ post.title }}
            </ion-card-title>
        </ion-card-header>
        <ion-card-content>
            <ion-img :src="image"></ion-img>
            <ion-button @click="$router.go(-1)">Go back</ion-button>
        </ion-card-content>
    </ion-card>
</template>

<script>
export default {
    props: ['post'],
    data() {
        return {
            image:'',
        }
    },
    mounted() {
        this.image = this.post.preview.images[0].source.url.split('&amp;').join('&');
    },
}
</script>


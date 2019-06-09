<template>
    <ion-card>
        <ion-item>
            <ion-label position="floating">Primer nombre</ion-label>
            <ion-input :value="greeting" @input=" greeting = $event.target.value"></ion-input>
        </ion-item>
        <ion-button color="primary" expand="full" @click="handleClick">Enviar</ion-button>
    </ion-card>
</template>

<script>
export default {
    data() {
        return {
            greeting: ''
        }
    },
    methods:{
        async handleClick(){
            const alert = await this.$ionic.alertController.create({
                header: '¿Desea enviar la información?',
                subHeader: 'Confirmar',
                message: `Desea enviar como nombre ${ this.greeting }?`,
                buttons: ['Cancel','Enviar']
            });

            await alert.present();
        }
    }
}
</script>
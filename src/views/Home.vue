<template>
  <ion-card>
      <ion-item>
          <ion-label position="floating">Primer nombre</ion-label>
          <ion-input></ion-input>
      </ion-item>
      <ion-button color="primary" expand="full" @click="handleClick">Enviar</ion-button>
  </ion-card>
</template>

<script>
export default {
    methods:{
        async handleClick(){
            const alert = await this.$ionic.alertController.create({
                header: '¿Desea enviar la información?',
                subHeader: 'Confirmar',
                message: 'Al presionar enviar no podrá editar los datos',
                buttons: ['Cancel','Enviar']
            });

            await alert.present();
        }
    }
}
</script>
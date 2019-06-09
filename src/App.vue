<template>
<div id="app">
  <ion-app>
    <ion-toolbar color="primary">
      <ion-buttons>
        <ion-button slot="secondary">
          <ion-icon name="logo-reddit"></ion-icon>
        </ion-button>
      </ion-buttons>
      <ion-title>
        Reddit Sport
      </ion-title>
    </ion-toolbar>
    <ion-content color="light">
      <router-view/>
    </ion-content>
  </ion-app>
</div>
</template>

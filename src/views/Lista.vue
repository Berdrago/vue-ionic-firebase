<template>
  <ion-page>
    <ion-header>
      <ion-toolbar  class="centrado">
         <!-- Titulo de  la pagina--> 
        <ion-title style="color:red" class="title" >Lista de productos</ion-title>
      </ion-toolbar>
    </ion-header>
  </ion-page>
</template>

<script lang="ts">
import { IonPage,IonLabel,IonInput,IonTitle,IonContent,IonItem,IonButton,IonBackButton, IonButtons,IonToolbar,IonHeader } from '@ionic/vue';
import { defineComponent } from 'vue';



export default defineComponent({
  name: 'Lista',
  components: {
    IonPage,
    IonLabel,
    IonInput,
    IonTitle,
   
  },
});
</script>
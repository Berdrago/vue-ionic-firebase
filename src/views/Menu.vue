<template>
  <ion-page>
    <ion-header>
      <ion-toolbar  style="colo:red" class="centrado">
        <ion-title style="color:red" > Menu</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-menu side="start" menu-id="custom" class="my-custom-menu" content-id="main">
      <ion-header>
        <ion-toolbar color="danger" class="centrado">
          <ion-title >Menu</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content >
        <ion-list>
          <ion-item-sliding  v-for="Catproducto in Catproductos" :key="Catproducto">
            <ion-item>
              <ion-label color="danger">{{Catproducto.name}} </ion-label>
            </ion-item>
            <ion-item-options side="end">
              <ion-item-option @click="unread(item)" color="danger"> <ion-icon :icon="handRightOutline" size="large" > </ion-icon> </ion-item-option>
            </ion-item-options>
          </ion-item-sliding>
       </ion-list>
      </ion-content>
    </ion-menu>
    <ion-router-outlet id="main"></ion-router-outlet>
  </ion-page>
</template>

<script lang="ts">
import { 
  IonPage,
  IonContent, 
  IonHeader, 
  IonItem, 
  IonList, 
  IonMenu, 
  IonRouterOutlet,
  IonTitle, 
  IonToolbar,
  menuController,
} from '@ionic/vue';
import { defineComponent } from 'vue';
import { handRightOutline,reorderThreeOutline} from 'ionicons/icons'
import { App } from '../App.vue';



export default defineComponent({
  name:'Menu',
  components: {
    IonPage,
    IonContent, 
    IonHeader, 
    IonItem, 
    IonList, 
    IonMenu, 
    IonRouterOutlet,
    IonTitle, 
    IonToolbar,
  },
  
    setup (){
    const  {Catproductos} = App ()
    
    menuController.enable(true, 'first');
    menuController.open('first');
    return {
      Catproductos,
      handRightOutline,
      menuController,
      reorderThreeOutline
    }
  }
});
</script>
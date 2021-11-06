<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent } from 'vue';
import { ref } from 'vue';

//Aqui importare axios para validar Usuarios
import axios from "axios";


  



//AQUI IMPORTARE FCM PARA  HACER LA CONEXION EN FIREBASE 
import { FCM } from "capacitor-fcm";
 const fcm = new FCM();
import { Plugins} from '@capacitor/core';
const { PushNotifications } = Plugins;


export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  },
  methods:{
    register(email: any, password: any) {
    const user = { email, password };
    const ENDPOINT_PATH = "https://reqres.in/api/";
    return axios.post(ENDPOINT_PATH + "register", user);
  },
  data: () => ({

  })

  },
  });
  
  
  
  export const App = () =>  {

    const Catproductos = ref([
        { id : 1,name: 'Pefil'},
        { id : 2,name: 'Cerrar Sesion'}
    ])
    

        return {
          Catproductos
          
        };
        
  };
  
  
  



</script>

  fcm
  .getToken()
  .then(r => alert(`Token ${r.token}`))
  .catch(err => console.log(err));


 async pushInit() {
    try {
      PushNotifications.addListener('registrationError', (error: any) =>          {
        console.log(`error on register ${JSON.stringify(error)}`);
      });
      
      PushNotifications.addListener('pushNotificationReceived',
        (notification: any) => {
          console.log(`notification      ${JSON.stringify(notification)}`);
      });
      
      PushNotifications.addListener('pushNotificationActionPerformed',
    async (notification: any) => {
      // Do something
      });
      PushNotifications.register();
      const fcmToken = await fcm.getToken();
      } catch (e) {
        console.log(e);
    }
  },
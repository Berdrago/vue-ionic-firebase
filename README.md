# vue-ionic-firebase
Aplicacion Hibrida
Proyecto vue-ionic-firebase

#Objetivos de la Aplicacion
Crear aplición híbrida con framework ionic
Conectar aplicación con Firebase y generar notificación Push

#Requisitos 
Instalar node js
Instalar Ionic 
Instalar visual studios o Editor de codigo a preferencia 
#--------------Crear Proyecto----------------
ionic start vue-ionic-firebase  blank --type vue
--------------Levantar servicio-------------
ionic serve 
ionic serve -lab
--------------Integrar Capacitor----------------
ionic integrations enable capacitor 
ionic cap add android
--------------Integrar FCM----------------------
npm i capacitor-fcm
--------------Importar firabase--------------------
npm install --save firebase-admin
-----------------Compilar -----------------------------------
ionic cap sync

#Author
Dread/Berdrago




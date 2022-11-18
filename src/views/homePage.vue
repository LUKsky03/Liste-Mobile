<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Liste de course</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>
      <div id="containerProduct">
            <ion-label>Liste 1</ion-label>
            <ion-grid class="ion-margin-bottom">
              <ion-row class="ion-padding-start ion-padding-end">
                <ion-col>
                  <ion-item>
                    <ion-label position="floating">Nom du produit</ion-label>
                    <ion-input type="text" v-model="txtname" placeholder="Nom" class="inputPrenom"></ion-input>
                  </ion-item>
                </ion-col>
                <ion-col class="colBtn">
                  <ion-button shape="round" expand="full" class="ion-align-self-end" @click="addProduct">Ajouter</ion-button>
                </ion-col>
              </ion-row>
            </ion-grid>
            <ion-item data-id="1" class="ion-margin-top">
              <ion-checkbox slot="start"></ion-checkbox>
              <ion-label>exemple</ion-label>
            </ion-item>
        </div>
    </ion-content>
  </ion-page>
</template>

<script>
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent,IonButton,IonCheckbox,IonLabel,IonItem,IonInput } from '@ionic/vue';

export default  defineComponent({
  name: 'Tab1Page',
  components: {  IonHeader, IonToolbar, IonTitle, IonContent, IonPage,IonButton,IonCheckbox,IonLabel,IonItem,IonInput },
  setup(){
      return{
        txtname:""
      }
  },
  methods:{
      addProduct(){
        let nom = (this.txtname !== '') ? this.txtname : 'produit';
        document.getElementById('containerProduct').insertAdjacentHTML('beforeend',`
        <ion-item data-id="1" class="ion-margin-top">
              <ion-checkbox slot="start"></ion-checkbox>
              <ion-label>`+nom+`</ion-label>
            </ion-item>
        `)
      }
  }

});

</script>

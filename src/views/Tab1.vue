<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>

      <ExploreContainer name="Tab 1 page" />
      <p v-if="age >= 18">You are an adult</p>
      <li v-for="user in users" v-bind:key="user.id">{{ user }}</li>
      <!-- <p v-on:click="handleEvent"> click me to see value of email</p> -->

      <!-- short form for event handlers -->
      <ion-item>
        <ion-input type="text" placeholder="enter your email" v-model="email">
        </ion-input>
      </ion-item>
      <ion-button @click="handleEvent">click me to see value of email</ion-button>

    </ion-content>
  </ion-page>
</template>
<script>
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonItem,
  IonInput,
  IonButton,
} from "@ionic/vue";
import ExploreContainer from "@/components/ExploreContainer.vue";

export default {
  name: "Tab1",
  components: {
    ExploreContainer,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonItem,
    IonInput,
    IonButton,
    IonPage,
  },
  data() {
    return {
      age: 16,
      users: [
        {
          id: 1,
          name: "abc",
        },
        {
          id: 2,
          name: "abc",
        },
        {
          id: 3,
          name: "abc",
        },
      ],
      email: "",
    };
  },
  methods: {
    handleEvent() {
      console.log(this.email);
    },
  },
};
</script>
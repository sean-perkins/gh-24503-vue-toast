<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet, toastController } from '@ionic/vue';
import { defineComponent, onMounted } from 'vue';

async function toast() {
  const t = await toastController.create({
    message: 'hello'
  });
  t.present();
}

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  },
  setup() {
    onMounted(() => {
      toast();
    })
  }
});
</script>
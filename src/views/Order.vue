<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-back-button default-href="/" slot="start"></ion-back-button>
        <ion-title>Orders</ion-title>
        <ion-text color="secondary" slot="end">
          <!-- DOWNLOAD ORDERS -->
        </ion-text>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <ion-searchbar />
      <hr />
      <div class="order">
        <div class="order-header">
          <div class="oreder-id">
            <ion-item lines="none">
              <ion-label>
                <h1>Order ID</h1>
                <p>Customer Name</p>
              </ion-label>
            </ion-item>
          </div>
          <div class="order-tags">
            <ion-chip>
              <ion-icon :icon="pricetag" />
              <ion-label>Shopify ID</ion-label>
            </ion-chip>
            <ion-chip>
              <ion-icon :icon="pricetag" />
              <ion-label>Customer Loyalty Status</ion-label>
            </ion-chip>
          </div>

          <div class="order-metatags">
            <ion-label>
              <ion-note>Ordered on 7 Jan 2021</ion-note>
              <ion-badge color="primary">Approved</ion-badge>
            </ion-label>
          </div>
        </div>
        <div class="order-items">
          <ion-card>
            <ion-item>
              <ion-thumbnail>
                <Image />
              </ion-thumbnail>
              <ion-label>
                <h2>Brand</h2>
                <h1>Virtual Name</h1>
                <p>Color: color</p>
                <p>Size: size</p>
                
              </ion-label>
              <ion-note color="success">15 in Stock</ion-note>
            </ion-item>
            <ion-item>
              <ion-label> Promise date </ion-label>
              <ion-text slot="end"> 14 Jan 2021 </ion-text>
            </ion-item>
            <ion-item>
              <ion-label> Promise date </ion-label>
              <ion-text slot="end"> 14 Jan 2021 </ion-text>
            </ion-item>
            <ion-item>
              <ion-label> Promise date </ion-label>
              <ion-text slot="end"> 14 Jan 2021 </ion-text>
            </ion-item>
          </ion-card>
        </div>
      </div>
    </ion-content>
  </ion-page>
</template>

<script>
import Image from "../components/Image.vue";
import {
  IonBackButton,
  IonTitle,
  IonText,
  IonToolbar,
  IonHeader,
  IonSearchbar,
  IonLabel,
  IonItem,
  IonChip,
  IonCard,
  IonThumbnail,
  IonBadge,
  IonPage,
  IonNote,
  IonIcon,
  IonContent,
} from "@ionic/vue";
import { pricetag, ribbon } from "ionicons/icons";
import { setup } from "axios-cache-adapter";
export default {
  name: "Order",
  components: {
    Image,
    IonBackButton,
    IonTitle,
    IonText,
    IonToolbar,
    IonHeader,
    IonSearchbar,
    IonLabel,
    IonItem,
    IonChip,
    IonCard,
    IonThumbnail,
    IonBadge,
    IonIcon,
    IonNote,
    IonPage,
    IonContent,
  },
  setup() {
    return {
      pricetag,
      ribbon,
    };
  },
};
</script>
<style scoped>
.order-id {
  grid-area: id;
}

.order-metadata {
  grid-area: metadata;
  /* max-width: min-content; */
  justify-self: end;
  padding-right: 10px;
}
.order-header {
  display: grid;
  grid: "id tags metadata" / max-content 1fr minmax(min-content, max-content);
  align-items: center;
}
.order-tags {
  grid-area: tags;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>

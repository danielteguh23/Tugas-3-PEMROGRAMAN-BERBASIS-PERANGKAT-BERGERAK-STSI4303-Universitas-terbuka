<template>
  <ion-content>
    <div class="container">

      <button class="refresh-btn" @click='fetchData'>
  <ion-spinner v-if="loading" name="crescent">  </ion-spinner>   
    <span v-else>refresh</span>
   </button>

<div v-if="loading" class="loading-text">
loading...
</div>

<div v-else>
  <div
  class="crypto-card"
  v-for=" coin in coins"
  :key="coin.id"
  >
<div class="left">
  <p class="rank-title">Rank</p>
  <p class="rank-number">{{ coin.rank }}</p>
</div>

<div class="middle">
  <p class="name">{{ coin.name }}</p>
  <p class="currency">USD</p>
 <p class="price">{{ coin.price_usd }}</p>

</div>

</div>

</div>

</div>
  </ion-content>
  </template>

  <script setup>
import {ref, onMounted} from "vue";
import { IonContent,IonSpinner } from "@ionic/vue";

const coins = ref([]);
const loading = ref(true);

async function fetchData() {
  loading.value = true;
  const url = "https://api.coinlore.net/api/tickers/";

  try {
    const response = await fetch (url);
    const data = await response.json();

    coins.value = data.data.slice(0, 7);
  } catch ( error) {
    console.error("error fetching",error);

  }
  loading.value =false;

}
onMounted(() => {
  fetchData();
});

</script>

<style>
.container {
  max-width: 420px;
  margin: 20px auto;
}

.refresh-btn {
  width: 100%;
  padding: 12px;
  background:#1c67ff;
  border: none;
  color: white;
  border-radius: 10px;
  font-size: 18px;
  cursor: pointer;
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
  gap: 8px;
}

.loading-text {
  text-align: center;
  font-size: 20px;
  padding: 20px;
}

.crypto-card {
  background: #fff3c8;
  border: 1px solid #d9c999;
  border-radius: 10px;
  padding: 12px;
  display: flex;
  margin-bottom: 12px;
}

.left, .middle, .right{
flex: 1;
}

.rank-title {
  font-size: 12px;
  color:#555;
}

.rank-number {
  font-size: 18px;
  font-weight: bold;
}

.name {
  font-size: 14px;
  color:#333;
}

.symbol {
  font-size: 20px;
  font-weight: bold;
  color: #555;
}

.currency {
  font-size: 12px;
  text-align: right;
  color:#555;
}

.price {
  font-size: 18px;
  font-weight: bold;
  text-align: right;
}
</style>

<script setup>
const route = useRoute();
const { data } = await useFetch('/api/ticker/?id=' + route.params.id);
const coin = data.value[0];
</script>
<template>
  <h2>{{ coin.name }}</h2>

  <table border="1px solid">
    <thead>
      <th>symbol</th>
      <th>Rank</th>
      <th>Price</th>
      <th>Market Cap - US $</th>
    </thead>
    <tr>
      <td>{{ coin.symbol }}</td>
      <td>{{ coin.rank }}</td>
      <td>{{ coin.price_usd }}</td>
      <td>{{ coin.market_cap_usd }}</td>
    </tr>
  </table>
</template>

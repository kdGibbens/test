<script setup>
const { data } = await useFetch('/api/tickers?limit=10');
</script>
<h1></h1>
<template>
  <table border="1px solid">
    <thead>
      <tr>
        <th>Name</th>
        <th>Symobol</th>
        <th>Price</th>
        <th>Details</th>
      </tr>
    </thead>
    <tr v-for="currency in data.data" v-bind:key="currency.id">
      <td>{{ currency.name }}</td>
      <td>{{ currency.symbol }}</td>
      <td>{{ currency.price_usd }}</td>
      <td>
        <NuxtLink :to="'/currency/' + currency.id">{{ currency.id }}</NuxtLink>
      </td>
    </tr>
  </table>
</template>

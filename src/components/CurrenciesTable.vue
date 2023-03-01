<template>
  <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
    <!-- Using utilities: -->
    <div class="container mx-auto">
      <table class="w-full text-left text-sm text-gray-500 dark:text-gray-400">
        <thead
          class="bg-gray-50 text-xs uppercase text-gray-700 dark:bg-gray-700 dark:text-gray-400"
        >
          <tr>
            <th scope="col" class="px-6 py-3">Rank</th>
            <th scope="col" class="px-6 py-3">Name</th>
            <th scope="col" class="px-6 py-3">Symbol</th>
            <th scope="col" class="px-6 py-3">Id</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(currency, index) in currencies"
            :key="currency.id"
            class="border-b bg-white dark:border-gray-700 dark:bg-gray-900"
          >
            <th
              scope="row"
              class="whitespace-nowrap px-6 py-4 font-medium text-gray-900 dark:text-white"
            >
              {{ index }}
            </th>
            <td class="px-6 py-4">{{ currency.name }}</td>
            <td class="px-6 py-4">{{ currency.symbol }}</td>
            <td class="px-6 py-4">{{ currency.id }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'CurrenciesTable',
  data() {
    return {
      currencies: [],
      errors: []
    }
  },
  methods: {
    fetchData() {
      axios
        .get('https://api.coingecko.com/api/v3/coins/list')
        .then((response) => {
          console.log('---Success---')
          this.currencies = response.data
        })
        .catch((error) => {
          console.log('---Failed---')
          this.errors.push(errors)
        })
    }
  },
  created() {
    this.fetchData()
  }
}
</script>
<style></style>

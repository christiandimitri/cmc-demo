<template>
  <div class="about">
    <CurrenciesTable />
  </div>
</template>
<script>
import CurrenciesTable from '@/components/CurrenciesTable.vue'
export default {
  components: {
    CurrenciesTable
  }
}
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

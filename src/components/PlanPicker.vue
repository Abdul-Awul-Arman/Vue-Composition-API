<script setup>
import { ref } from 'vue'
import CoffeePlan from './CoffeePlan.vue'
const plans = ref(['The Single', 'The Curious', 'The Addict'])

let selected = ref()

function handle(name) {
  selected.value = name
}
</script>
<template>
  <div class="plans">
    <CoffeePlan
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      @selected="handle($event)"
      :selected="plan===selected"
    />
  </div>
</template>

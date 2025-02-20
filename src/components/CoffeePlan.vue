<script setup>
import { defineEmits } from 'vue'

const props = defineProps({
  name: {
    type: String,
    required: true,
  },
  selected: {
    type: Boolean,
    required: true,
    default:false,
  },
})
const emit = defineEmits('selected')

function handler() {
  emit('selected',props.name)
}
</script>
<template>
  <div class="plan" @click="handler" :class="{ 'active-plan': selected }">
    <div class="description">
      <span class="title">{{ props.name }} </span>
    </div>
  </div>
</template>

<script setup>
defineProps({
  disabled: Boolean,
  name: { type: String, required: true },
  icon: { type: String, required: true },
  sizeClasses: { type: String, default: 'w-8 h-8' },
});

defineEmits(['click']);
</script>

<template>
  <button
    class="flex flex-col items-center justify-center rounded-md text-fog"
    :class="[
      sizeClasses,
      disabled ? 'bg-slate-800' : 'bg-blood hover:bg-fog hover:text-blood',
    ]"
    :disabled="disabled"
    :name="name"
    @click="$emit('click')"
  >
    <span class="sr-only">{{ name }}</span>
    <Icon :name="icon" />
  </button>
</template>

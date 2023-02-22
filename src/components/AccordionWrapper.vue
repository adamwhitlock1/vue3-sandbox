<script setup>
defineProps(["accordionItems", "selectAccordion"]);
</script>

<template>
  <div class="accordion-wrapper">
    <div
      class="accordion-item my-1"
      v-for="(item, index) in accordionItems"
      :key="index"
    >
      <div
        class="bg-gray-200 flex items-center justify-between py-2 px-4 cursor-pointer"
        @click="selectAccordion(index)"
      >
        <h3 class="text-lg">{{ item.title }}</h3>
        <div class="w-6 h-6" :class="item.active ? 'rotate-180' : ''">
          <img src="../assets/arrow-down.svg" alt="arrow-down" />
        </div>
      </div>
      <div :class="item.active ? 'block' : 'hidden'">
        <p class="px-2 py-4">{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

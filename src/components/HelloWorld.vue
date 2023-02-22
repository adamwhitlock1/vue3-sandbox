<script setup>
import { ref, reactive } from "vue";
import AccordionWrapper from "./AccordionWrapper.vue";

const state = reactive({
  accordionItems: [
    {
      title: "What is a dog?",
      text: "A dog is a type of domesticated animal. Known for its loyalty and faithfulness, it can be found as a welcome guest in many households across the world.",
      active: true,
    },
    {
      title: "What kinds of dogs are there?",
      text: "There are many breeds of dogs. Each breed varies in size and temperament. Owners often select a breed of dog that they find to be compatible with their own lifestyle and desires from a companion.",
      active: false,
    },
    {
      title: "How do you acquire a dog?",
      text: "Three common ways for a prospective owner to acquire a dog is from pet shops, private owners, or shelters.",
      active: false,
    },
  ],
});

const selectAccordion = (index) => {
  state.accordionItems.forEach((item, i) => {
    if (i === index) {
      item.active = !item.active;
    } else {
      item.active = false;
    }
  });
};

defineProps({
  msg: String,
});

const count = ref(0);
</script>

<template>
  <AccordionWrapper
    :accordionItems="state.accordionItems"
    :selectAccordion="selectAccordion"
  />
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>

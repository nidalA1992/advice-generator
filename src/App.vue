<script setup>
import AdviceCard from "@/components/advice-card.vue";
import AppLayout from "@/components/app-layout.vue";
import { onMounted, ref } from "vue";

const slipObj = ref({});
const isLoading = ref(false);

const fetchAdvice = async () => {
  isLoading.value = true;
  const res = await fetch("https://api.adviceslip.com/advice");
  const { slip } = await res.json();
  slipObj.value = slip;
  isLoading.value = false;
};

onMounted(() => {
  fetchAdvice();
});
</script>

<template>
  <app-layout>
    <advice-card
      :is-loading="isLoading"
      :fetch-advice="fetchAdvice"
      :slip="slipObj"
    />
  </app-layout>
</template>

<script setup>
import PatternIcon from "@/components/icons/pattern-icon.vue";
import DiceIcon from "@/components/icons/dice-icon.vue";

defineProps({
  fetchAdvice: Function,
  slip: Object,
  isLoading: Boolean,
});
</script>

<template>
  <div class="card">
    <h2 class="advice-title">advice # {{ slip.id }}</h2>
    <p class="advice-text">
      {{ slip.advice }}
    </p>
    <pattern-icon />
    <button @click="fetchAdvice" class="dice-button">
      <div v-if="isLoading" class="loader"></div>
      <dice-icon v-else />
    </button>
  </div>
</template>

<style lang="scss">
$mb: 25px;
.loader {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  border: 1px solid var(--dark-blue);
  border-top-color: transparent;
  animation: rotate infinite 1000ms linear;
  @keyframes rotate {
    from {
      rotate: 0;
    }
    to {
      rotate: 360deg;
    }
  }
}

.advice-title {
  font-size: 14px;
  text-transform: uppercase;
  color: var(--neon-green);
  margin-bottom: $mb;
  letter-spacing: 0.2em;
}

.advice-text {
  color: var(--light-cyan);
  text-align: center;
  font-size: 22px;
  margin-bottom: $mb;
}

.card {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 40px 20px 60px;
  border-radius: 10px;
  background-color: var(--dark-grayish-blue);
  max-width: 600px;
}

.dice-button {
  position: absolute;
  bottom: -27.5px;
  left: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  padding: 0;
  width: 55px;
  height: 55px;
  line-height: 1;
  background-color: var(--neon-green);
  border: none;
  cursor: pointer;
  transition: box-shadow 150ms ease-out;
  transform: translateX(-50%);
  outline: none;

  &:hover {
    box-shadow: 0 0 30px 3px var(--neon-green);
  }

  &:active {
    box-shadow: 0 0 30px 3px var(--light-cyan);
    background-color: var(--light-cyan);
  }
}

@media (min-width: 768px) {
  .card {
    max-width: 500px;
    padding: 45px 45px 60px;
  }
}
</style>

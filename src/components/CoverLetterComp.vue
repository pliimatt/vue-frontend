<template>
  <div class="container" id="grid">
    <button class="ExitBtn" @click="$emit('exit')">X</button>
    <div class="upper">
      <h2>Cover letter</h2>
      <p>{{ covLetterText }}</p>
    </div>
    <div class="lower-left">
      <h3>Contact me through e-mail.</h3>
      <a :href="addr">Send e-mail</a>
    </div>
    <div class="lower-right">
      <h3>Why me?</h3>
      <p>{{ motivText }}</p>
    </div>
  </div>
</template>

<script>
export default {
  emits: ["exit"],
  props: {
    addr: {
      type: String,
      required: true,
    },
    covLetterText: {
      type: String,
      required: true,
    },
    motivText: {
      type: String,
      required: true,
    },
  },
};
</script>

<style>
</style>
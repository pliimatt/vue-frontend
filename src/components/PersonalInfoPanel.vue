<template>
  <div class="infoPanel">
    <h3>{{ name }}</h3>
    <p>{{ addr }}</p>
    <p>{{ postPlace }}</p>
    <p>{{ phone }}</p>
    <p>{{ email }}</p>
  </div>
</template>

<script>
export default {
  props: {
    name: { type: String, required: true },
    addr: { type: String, required: true },
    postPlace: { type: String, required: true },
    phone: { type: String, required: true },
    email: { type: String, required: true },
  },
};
</script>

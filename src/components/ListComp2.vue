<template>
  <button class="ToggleBtn" @click="showComp = !showComp">
    {{ "Toggle " + naming }}
  </button>
  <ul v-if="showComp">
    <li v-for="(item, index) in itemList" :key="index" class="ListItem">
      <h2>{{ item.title }}</h2>
      <p class="description">{{ item.desc }}</p>
      <p class="date" v-if="item.date">{{ item.date }}</p>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    naming: {
      type: String,
      required: true,
    },
    itemList: {
      type: Array,
      required: true,
    },
  },
  data() {
    return { showComp: false };
  },
};
</script>

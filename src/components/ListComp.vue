<template>
  <div id="ListComp">
    <list-comp-2 naming="education" :itemList="edu" />
    <list-comp-2 naming="jobs" :itemList="jobs" />
    <list-comp-2 naming="IT skills" :itemList="ITs" />
  </div>
</template>

<script>
import ListComp2 from "./ListComp2.vue";
export default {
  components: { ListComp2 },
  props: {
    edu: {
      type: Array,
      required: true,
    },
    jobs: {
      type: Array,
      required: true,
    },
    ITs: {
      type: Array,
      required: true,
    },
  },
};
</script>

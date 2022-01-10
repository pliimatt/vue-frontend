<template>
  <div class="building">
    <p>
      {{ numberWithCommas(owned) }} X Tier {{ numberWithCommas(buildingTier) }},
      each giving {{ numberWithCommas(buildingGain) }} /sec for a total of
      {{ numberWithCommas(owned * buildingGain) }} /sec
    </p>
    <button @click="buyBuilding" :disabled="buildingCost > currency">
      Buy ({{ buildingCost }})
    </button>
  </div>
</template>

<script>
export default {
  props: {
    currency: {
      type: Number,
      required: true,
    },
    buildingTier: {
      type: Number,
      required: true,
    },
  },
  emits: ["buy", "cgain"],
  data() {
    return {
      owned: 0,
    };
  },
  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
    buyBuilding() {
      const cost = this.buildingCost;
      if (this.currency >= cost) {
        this.$emit("buy", cost);
        this.owned++;
        this.$emit("cgain", this.buildingGain);
      }
    },
  },
  computed: {
    buildingCost() {
      return (this.owned + 1) * 10 ** this.buildingTier;
    },
    buildingGain() {
      return 5 ** (this.buildingTier - 1);
    },
  },
};
</script>

<style>
</style>
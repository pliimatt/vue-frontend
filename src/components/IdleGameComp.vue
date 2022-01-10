<template>
  <div class="GameWindow">
    <p>Idle clicker game</p>
    <button @click="currency = currency + 1">Increment</button>
    <p>
      Current amount of currency: {{ numberWithCommas(currency) }}, gaining
      {{ numberWithCommas(cgain) }} /sec
    </p>
    <building-comp
      v-for="b in buildingTiers"
      :key="b"
      :currency="currency"
      :buildingTier="b"
      @buy="
        (cost) => {
          currency = currency - cost;
        }
      "
      @cgain="
        (gain) => {
          cgain = cgain + gain;
        }
      "
    />
  </div>
</template>

<script>
import BuildingComp from "./BuildingComp.vue";
import "../assets/IdleGame.css";

export default {
  components: { BuildingComp },
  data() {
    return {
      currency: 0,
      cgain: 0,
      buildingTiers: [],
      interval: null,
    };
  },
  methods: {
    numberWithCommas(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
  watch: {
    cgain: function () {
      if (this.interval) {
        clearInterval(this.interval);
      }
      this.interval = setInterval(() => {
        this.currency = this.currency + this.cgain;
      }, 1000);
    },
  },
  mounted() {
    for (let i = 1; i <= 10; i++) {
      this.buildingTiers.push(i);
    }
  },
};
</script>

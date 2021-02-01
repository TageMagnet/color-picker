<template>
  <ul>
    <li v-for="color in colors" :key="color" @click="$emit('click', color)">
      {{ color }}
    </li>
  </ul>
</template>

<script>
export default {
  props: ["match"],
  data() {
    return {
      //colors: ['red','green','blue'] // Change this to a vuex getter that filters based on this.match
    };
  },
  computed: {
    colors() {
      return this.$store.getters.firstN(4);
    },
  },
};
</script>

<style scoped lang="scss">
ul {
  position: absolute;
}
</style>
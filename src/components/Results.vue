<template>
  <p class="badge mt-3"
     :class="{'badge-success': rank==='Great', 'badge-warning': rank==='Good', 'badge-danger': rank==='Not Bad'}">
    {{ rank }}</p>
  <br>
  <p class="badge badge-light mt-1">Reaction Time is <span class="badge" :class="{'badge-success': rank==='Great', 'badge-warning': rank==='Good', 'badge-danger': rank==='Not Bad'}">{{ score }} ms</span></p>
</template>

<script>
export default {
  name: "Results",
  props: ['score'],
  data() {
    return {
      rank: null
    }
  },
  mounted() {
    if (this.score <= 450) {
      this.rank = 'Great'
    } else if (this.score < 600) {
      this.rank = 'Good'
    } else {
      this.rank = 'Not Bad'
    }
  }
}
</script>

<style scoped>
p {
  font-size: 25px;
}
</style>
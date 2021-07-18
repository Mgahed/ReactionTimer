<template>
  <div id="block" class="block" v-if="show_block" @click="stop_timer">Click Me</div>
</template>

<script>
export default {
  props: ['delay'],
  data() {
    return {
      show_block: false,
      timer: null,
      reaction_time: 0,
    }
  },
  methods: {
    start_timer() {
      this.timer = setInterval(() => {
        this.reaction_time += 10
      }, 10)
    },
    stop_timer() {
      clearInterval(this.timer)
      this.$emit('end', this.reaction_time)
      console.log(this.reaction_time)
    }
  },
  mounted() {
    setTimeout(() => {
      this.show_block = true
      this.start_timer()
    }, this.delay);

    setTimeout(() => {
      let top = Math.floor((Math.random() * 60) + 15);
      let left = Math.floor((Math.random() * 70) + 1);
      $('.block').css({'top': top+'%', 'left': left+'%'});
    }, this.delay + 1)
  },
  updated() {
    // console.log("Block component Updated")
  },
  name: "Block"
}
</script>

<style>
.block {
  position: absolute;
  top: 15%;
  left: 1%;
  width: 30%;
  max-height: 20%;
  border-radius: 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
  cursor: pointer;
}
</style>
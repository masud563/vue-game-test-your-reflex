<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me</div>
</template>

<script>
export default {

  props: ['delay'],

  data() {
    return{
      showBlock: false,
      timer: null,
      reactionTime: 0

    }
  },

  mounted() {
    setTimeout(()=>{
      this.showBlock = true
      this.timer = setInterval(() => {
        this.reactionTime += 10
      },10)
    },this.delay)
  },

  methods: {

    stopTimer() {
      clearInterval(this.timer)
      this.showBlock = false
      this.$emit('end',this.reactionTime)
    }
  }


}
</script>

<style>
  .block {
    display: inline-block;
    background-color: rgb(40, 153, 138);
    border-radius: 20px;
    margin: 60px auto;
    padding: 100px 150px ;
    color: white;
  }
</style>
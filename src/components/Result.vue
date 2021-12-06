<template >
  <div class="result">
    <p>Reaction time - {{ this.score }} ms</p>
  <h1>{{ giveVerdict(score) }}</h1>
  </div>
</template>

<script>
export default {

  props: ['score'],

  data() {
    return{
      comment: ['...Snail Pace', 'Rapid Reflexes!!!']
    }
  },

  methods: {
    giveVerdict(score){
      if(score>400){
        return this.comment[0]
      }
      else{
        return this.comment[1]
      }
    }
  }

}
</script>

<style>

  .result h1 {
    color:rgb(46, 172, 103)
  }

</style>
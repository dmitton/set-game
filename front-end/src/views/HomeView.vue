<template>
  <div class="home">
    <div class="start-game">
      <button @click="startGame()">New Game</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  data() {
   return {
     gameArray: [],
   }
  },
  methods: {
    //start the game
    startGame(){
      //get four cards and put them in the game card list
      this.getFourCards();
      //get matches to each of those four cards in the list
      this.putMatchestoCards();
    },
    getFourCards(){
      for (let i = 0; i < 4; i++){
        //get a random index
        var index = Math.floor(Math.random()*81);
        //push it onto the game card list
        this.gameArray.push(this.$root.$data.cards[index]);
      }
    },
    putMatchestoCards(){

    }
  }

}
</script>

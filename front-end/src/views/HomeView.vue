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
     cardsSelected: [],
   }
  },
  methods: {
    //start the game
    startGame(){
      //get four cards and put them in the game card list
      this.getGameCards();
      //get matches to each of those four cards in the list
      this.putMatchestoCards();

      //TODO check if selected cards are a match

    },
    getGameCards(){
      for (let i = 0; i < 12; i++){
        //get a random index
        var index = Math.floor(Math.random()*81);

        //TODO check to make sure the card isn't grabbed
        
        //push it onto the game card list
        this.gameArray.push(this.$root.$data.cards[index]);
      }
      //prints out the array
      console.log(this.gameArray);
    },
    putMatchestoCards(){
       
    },

    //TODO cardClickedCounter
    cardClickedCounter(){
      //check how many cards are clicked
      //if 3 cards are selected return true
    },

    //TODO selected cards are a match
    isSet(){

    }
  }

}
</script>

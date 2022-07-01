<template>
  <div class="home">
    <div class="start-game">
      <button @click="startGame()">New Game</button>
    </div>
    <div class="cards-displayed" v-for="card in gameArray" :key="card.id">
      <div class="photo-image">
       <p>{{card.pictureUrl}}</p>
       <img :src="card.pictureUrl" />
      </div>
      
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
      //get 12 cards and put them in the game card list
      this.getGameCards();

      //TODO check if selected cards are a match

    },
    getGameCards(){
      this.gameArray = [];
      for (let i = 0; i < 12; i++){
        //get a random index
        var index = Math.floor(Math.random()*81);

        //check to make sure the card isn't grabbed
        let result = true;
        //a while loop to keep looping to make sure that a card is not grabbed 
        while(result != false){
          result = this.checkForDuplicateCard(this.$root.$data.cards[index].id);
          if(result === false){
            //push it onto the game card list
            this.gameArray.push(this.$root.$data.cards[index]);
            break;
          }
          else{
            index = Math.floor(Math.random()*81);
          }
        }
      }
      //prints out the array
      console.log(this.gameArray);
    },

    //function that checks to see if the card is already in the game list
    checkForDuplicateCard(gameId) {
      for(let i = 0;i < this.gameArray.length; i++){
        if(this.gameArray[i].id === gameId){
          return true;
        }
      }
      return false;
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

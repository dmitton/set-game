<template>
  <div id="app">
   <div class="header">
   <div class="section-head">
    <div class="half-circle">
     <i class="fa fa-lightbulb-o" aria-hidden="true">Set Game</i>
    </div>
    <hr class="left">
    <hr class="right">
   </div>
  </div>
  <div class="content">
    <router-view />
  </div>
  </div>
</template>

<style>
.half-circle i{
  display: inline-block;
  transform: rotate(-15deg);
  position: absolute;
  top: 20px;
  left: 35px;
  font-size: 2em;
  padding-right: 10px;
}



hr{
  background-color: black;
  border: 1px solid black;
}

hr.left{
  width: 95px;
  position: absolute;
  left: 0;
  top: 28px;
}

hr.right{
  width:calc(100% - 200px);
  position: absolute;
  left: 194px;
  top: 55px;
}

.section-head{
  position: relative;
}

  .half-circle {
    width: 100px;
    height: 50px; /* as the half of the width */
    border-top-left-radius: 110px;  /* 100px of height + 10px of border */
    border-top-right-radius: 110px; /* 100px of height + 10px of border */
    border: 2px solid black;
    border-bottom: 0;
    transform: rotate(15deg);
    margin-left: 100px;
}
.content{
padding-top: 100px;
}
</style>

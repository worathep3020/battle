<template>
  <div>
    <button  @click ="start()" class="btn btn-dark btn btn-outline-success" >Start </button>
    <button  @click ="attack()" class="btn btn-dark btn btn-outline-success" >Attack</button>
    <button  @click ="SpecialAttack()" class="btn btn-dark btn btn-outline-success" >Special Attack</button>
    <button  @click ="Reset()" class="btn btn-dark btn btn-outline-success" >New game</button>
    <div class="row">
      <div class="col">
        <img v-bind:style="{width: aPlayer.hp +'px'}" :src="hp1" alt height="200px">
        <p>{{thp}}{{aPlayer.hp}}</p>
        <p><img style="width:30%" :src ="aPlayer.image"/></p>
        <br>
        <p>{{aPlayer.name}}</p>
        </div>
        <div class="font">
          <br>
          <br>
      <div v-if="aPlayer.hp <=0">YOU LOSE
        <p><button  @click ="Reset()" class=" btn btn-success" >Try again</button></p></div>
      <div v-else-if="aMonster.hp <=0">YOU WIN</div>
      </div>
        <div class="col">
        <img v-bind:style="{width: aMonster.hp +'px'}" :src="hp1" alt height="200px">
        <p>{{thp}}{{aMonster.hp}}</p>
        <p><img style="width:30%" :src ="aMonster.image"/></p>
        <br>
        <p>{{aMonster.name}}</p>
        </div>
      </div>
    <img src="https://mcdn.wallpapersafari.com/medium/47/53/L5lXu7.jpg" width="700">
      
      
    
   
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      thp: "HP:",
      end: false,
      hp1:
        "https://pngimage.net/wp-content/uploads/2018/06/health-bar-png-9.png",
      hp2:
        "https://pngimage.net/wp-content/uploads/2018/06/health-bar-png-9.png",
      aPlayer: { name: "" , hp: 1, image: ''},
      player: [
        { name: "Solgaleo", hp: 300, image: "https://www.pokencyclopedia.info/sprites/3ds/ani_7/3ani__791__sm.gif" },
        { name: "Blastoise", hp: 240 ,image: "https://projectpokemon.org/images/normal-sprite/blastoise-mega.gif"},
        { name: "Xerneas", hp: 310 ,image:  "https://www.pokencyclopedia.info/sprites/3ds/ani_6/3ani__716-active__xy.gif" },
        { name: "Kyurem-black", hp: 350 ,image: "https://projectpokemon.org/images/normal-sprite/kyurem-black-overdrive.gif" },
        { name: "Lugia", hp: 320 ,image: "https://projectpokemon.org/images/normal-sprite/lugia.gif" },
        { name: "Sceptile ", hp: 332 ,image: "https://www.pokencyclopedia.info/sprites/3ds/ani-b_6/3a-b__254-mega__oras.gif" },
        { name: "Rayquaza", hp: 400 ,image: "https://projectpokemon.org/images/normal-sprite/rayquaza-mega.gif" },
      ],
       aMonster: { name: "" , hp: 1, image: ''},
      monster: [
        { name: "Lunala", hp: 300 ,image: "https://www.pokencyclopedia.info/sprites/3ds/ani_7/3ani__792__sm.gif" },
        { name: "Hoopa", hp: 240 ,image: "https://projectpokemon.org/images/normal-sprite/hoopa-unbound.gif" },
        { name: "Palkia", hp: 310 ,image: "https://www.pokencyclopedia.info/sprites/3ds/ani_6/3ani__484__xy.gif" },
        { name: "Blaziken", hp: 250 ,image: "https://www.pokencyclopedia.info/sprites/3ds/ani_6/3ani__257-mega__xy.gif" },
        { name: "Kyurem-white", hp: 350 ,image: "https://projectpokemon.org/images/normal-sprite/kyurem-white-overdrive.gif" },
        { name: "Groudon", hp: 332 ,image: "https://projectpokemon.org/images/normal-sprite/groudon-primal.gif" },
        { name: "Giratina", hp: 400 ,image: "https://projectpokemon.org/images/normal-sprite/giratina-origin.gif" },
      ],
      pmax: "",
      mmax: "",
    };
  },
  methods: {
    random: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start:function(){
         
        this.aPlayer = this.player[this.random(1,7)-1 ]
        this.aMonster = this.monster[this.random(1,7)-1 ]
        
    },
    attack:function(){
        this.pmax = Math.floor(Math.random() * 10 + 4);
      this.aMonster.hp = this.aMonster.hp - this.mmax;
      this.mmax = Math.floor(Math.random() * 10 + 4);
      this.aPlayer.hp = this.aPlayer.hp - this.mmax;
      if (this.aPlayer.hp <= 0) {
        this.aPlayer.hp = 0;
        this.end = true;
      } else if (this.aMonster.hp <= 0) {
        this.aMonster.hp <= 0;
        this.end = true;
      }
    },
    SpecialAttack:function(){
      this.pmax = Math.floor(Math.random() * 10 + 4);
      this.aMonster.hp = this.aMonster.hp - this.mmax;
      this.mmax = Math.floor(Math.random() * 10 + 4);
      this.aPlayer.hp = this.aPlayer.hp - this.mmax;
      if (this.aPlayer.hp <= 0) {
        this.aPlayer.hp = 0;
        this.end = true;
      } else if (this.aMonster.hp <= 0) {
        this.aMonster.hp <= 0;
        this.end = true;
      }
    },
    Reset: function() {
      window.location.reload();
    },
  },
};
</script>
<style >
div{
     color: rgb(255, 255, 255);
     font-size: 20px;
}
font{
  color:aliceblue;
  font-size: 30px;
}

</style>
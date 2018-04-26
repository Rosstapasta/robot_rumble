<template class='stuff'>
  <div id="app">

    <section class='title'>
      <h1 class='titles3'>Robot Rumble</h1>
      <div class='topButtons'>
        <button @click='viewswitch(true)'>Create</button>
        <button @click='viewswitch(false)'>Robots</button>
      </div>
    </section>

    <section v-show='showcreate'>
      <create :pushmonster='pushmonster'>
      </create>
    </section>

    <section v-show='!showcreate'>
      <monsters :monstersall='monstersall'>
      </monsters>
    </section>


  </div>
</template>

<script>

import Create from './comps/Create';
import Monsters from './comps/Monsters';
import Monster from './comps/Monster';

export default {
  
  data () {
    return {
      showcreate: true,
      monstersall: [{name: 'Guy', health: 10, attack: 3, picture: 5}, {name: 'Buddy', health: 13, attack: 2, picture: 79}, {name: 'friend', health: 7, attack: 5, picture: 45}]
    }
  },

  methods: {
    viewswitch(bool){
      this.showcreate = bool
      console.log(this.monstersall)
    },

    pushmonster(val){
      this.monstersall.push(val)
      console.log(this.monstersall)
    }
  },

  computed: {

  },

  components: {
        create: Create,
        monsters: Monsters,
        monster: Monster
    }
}

</script>

<style>

.stuff{
  background-color: rgb(180, 25, 25);
}

#app{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: rgb(241, 63, 63);
  min-height: 100vh;
}

h1{
  font-size: 2rem;
}

.title{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.topButtons{
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
}

.titles3{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  width: 400px;
  background-color: rgb(202, 183, 183);
  border-radius: 10px;
}

</style>

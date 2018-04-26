<template>
    <div>

        <section>
            <h2>#1 {{monster1}}</h2>
            <h2>#2 {{monster2}}</h2>
            <button @click='fight'>Battle Royale!!</button>
        </section>        

        <section>
            <monster v-for='(monster, i ) in monstersall' :key='i' :monster='monster' :selectmonster='selectmonster'>
            </monster>
        </section>

    </div>
</template>

<script>
import Monster from './Monster';

export default {

    data(){

        return {
            monster1: '',
            monster2: '',
            monsterfight: []
        }
    },

    methods: {
        fight(){
            var random = Math.floor(Math.random() * 2) + 1;
            if(random === 1){
                alert(`${this.monsterfight[0]} wins!`)
            }else{
                alert(`${this.monsterfight[1]} wins!`)
            }

            this.monster1 = '';
            this.monster2 = '';
            this.monsterfight = []
        },

        selectmonster(val){
            this.monsterfight.push(val);
            if(this.monster1 === ''){
                this.monster1 = val
            }else if(this.monster2 === ''){
                this.monster2 = val
            }
            console.log(this.monsterfight)
        }

    },

    components: {
        monster: Monster
    },

    props: ['monstersall']
}

</script>

<style>

</style>
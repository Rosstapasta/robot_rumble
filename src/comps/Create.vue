<template>
    <div>
        
        <section>
            <h3>Name</h3>
            <input v-model='name'>

            <h3>Health</h3>
            <input v-model='health'>

            <h3>Attack</h3>
            <input v-model='attack'>
        </section>

        <button @click='create'>Create</button>

    </div>
</template>

<script>
    export default {
        data(){

            return {
                name: '',
                health: 0,
                attack:0
            }
        },
        methods: {
            create(){
                var random = Math.floor(Math.random() * 100) + 1;
                this.pushmonster({name: this.name, health: this.health, attack: this.attack, picture: random })
            }
        },
        props: ['pushmonster']
    }

</script>

<style>

</style>

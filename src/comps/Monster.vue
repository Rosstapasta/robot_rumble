<template>
    <div>
        <section>
            <div class='robit'>

                <div class='ccc'>
                    <p>{{monster.name}}</p>
                    <p>Health: {{monster.health}}</p>
                    <p>Power: {{monster.attack}}</p>
                </div>

                <img v-bind:src="`https://robohash.org/${monster.picture}`" class='roboimg'/>
                <button @click='selectmonster(monster.name)' class='buttons'>add</button>
            </div>

        </section>
    </div>
</template>

<script>

export default {

    methods: {
        sendmonster(val){
            this.selectmonster(val)
        }
    },

    props: ['monster', 'selectmonster']
}

</script>

<style>
.robit{
    width: 300px;
    height: 150px;
    background-color: rgb(214, 155, 65);
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-bottom: 10px;
    margin-top: 10px;
    border-radius: 10px;

}

.ccc{
    display: flex;
    flex-direction: column;
}



.roboimg{
    width: 150px;

}

.buttons{
    height: 20px;
}

</style>
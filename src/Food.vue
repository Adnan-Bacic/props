<template>
    <div id="food">
        <h2>all food</h2>
            <div v-for="(foodItem, index) in food" v-bind:key="index">
                <p v-on:click="deleteFood(food.name)">{{ foodItem.name }}</p>
            </div>

            <h2>only vegan</h2>
            <div v-for="(foodItem, index) in food" v-bind:key="index">
                <p v-if="foodItem.vegan"> {{ foodItem.name }}</p>
            </div>
    </div>
</template>

<script>
export default {

    props: ['food'],

    data(){
        return{

        }
    },

    methods:{
        deleteFood(name){
            this.$emit('delete', { name: name })
        }
    }
}
</script>
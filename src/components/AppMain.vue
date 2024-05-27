<script>
import SingleCard from './SingleCard.vue';
import store from '../data/store.js';

export default {

    name: "AppMain",
    // SERVIVA PRIMA CHE NON AVEVO STORE.JS
    // components: {
    //     SingleCard,
    // },

    data() {
        return {

        }
    },

    methods: {

    },

    mounted() {

    }
}
</script>

<template>
    <main class="container px-5 py-2">
        <!-- SEZIONE SELECT -->
        <section id="input" class="container mb-2">
            <select name="type" id="" class="w-25 p-2">
                <option value="">Alien</option>
            </select>
        </section>
        <!-- SEZIONE CARD -->
        <section id="card" class="container bg-white p-4">
            <div class="content-card text-white">
                <div class="found p-2 bg-dark mx-1">
                    <h6 class="m-0 px-3">Found 39 Cards</h6>
                </div>
                <div class="row m-0 justify-content-between">
                    <SingleCard v-for="cardSingle in store.cards" :card="cardSingle" />
                </div>
            </div>
        </section>
    </main>
</template>

<style scoped>
main {
    background-color: #D48F38;
}
</style>
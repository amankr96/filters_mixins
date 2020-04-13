<template>
<div>
    <h1>Filters & Mixins</h1>
    <input v-model="filterText">
    <ul>
    <li v-for="item in filteredFruits" :key="item">{{ item }}</li>
    </ul>
    <hr>
    <app-list></app-list>
</div>
</template>

<script>
import { fruitMixin } from './fruitMixin.js';
    export default {

    mixins: [fruitMixin],
    created(){
        console.log('created_list');
    }

}
</script>

<style>

</style>

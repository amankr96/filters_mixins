<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                <p>{{ text | toUppercase | to-lowercase }}</p>
                
                <button @click="fruits.push('berries')">Add A new fruit</button>
                <hr>
                <input v-model="filterText">
                <ul>
                <li v-for="item in filteredFruits" :key="item">{{ item }}</li>
                </ul>
                <hr>
                <app-list></app-list>
            </div>
        </div>
    </div>
</template>

<script>
import List from './List.vue';
import { fruitMixin  } from './fruitMixin.js';

    export default {
        data(){
            return{
                text: 'Hello There',
            }
        },
        filters: {
            toUppercase(value){
                return value.toUpperCase();
            }
          },
          components: {
              appList: List
          },
          mixins:[fruitMixin] 
        }
</script>

<style>

</style>

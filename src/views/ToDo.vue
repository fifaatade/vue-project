<template>
    <!--<form>
        <h1>TO-DO-LIST</h1>
        <div class="to-do-list">
            <input type="checkbox" class="list">
            <label for="task1">lessive</label>
        </div>
        <div class="to-do-list">
            <input type="checkbox" class="list">
            <label for="task2">cuisine</label>
        </div>
    </form>!-->
    <!--<div :class="element.is_finished?'color':''" v-for="element in tab">  pour mettre une condition si et sinon --> 
    <form action="#" @submit.prevent="addToDo">
        <div id="task">
            <label for="task"> Quelle tache voulez-vous ajouter?</label>
            <input type="text" v-model="newToDo">
            <button > soumettre</button>
            <p class="barre"> {{ newToDo }}</p>
            <input type="checkbox" name="" id="" >
        </div>

        <!-- <div v-bind:class="{'color barre':element.is_finished}"  v-for="element in tab">
            <div v-if="element.is_finished">
                <p class="barre"> {{ element.name }}</p>
                <input type="checkbox"  :checked="element.is_finished" name="" id="" >
            </div>
            <div v-else>
                <p > {{ element.name }}</p>
                <input type="checkbox"  :checked="element.is_finished" name="" id="" >
            </div>
        </div> -->
    </form>
</template>

<script lang="ts" setup>
/* import { METHODS } from 'http';
import { VueElement } from 'vue'; */

import {ref} from 'vue';
const newToDo=ref('');
let tab=ref([
    {
        name:'lessive',
        is_finished:true
    },
    {
        name:'cuisine',
        is_finished:false
    },
    {
        name:'lessive',
        is_finished:true
    },
    {
        name:'cuisine',
        is_finished:false
    }
 ])
 function addToDo(){
    tab.value.push({name:newToDo.value,is_finished:false})
    newToDo.value=''
 }
/* new Vue{
    el:'#task',
    Data:{
        name:''
    },
    METHODS:{
        tache(){
            alert(this.name);
        }
    }
}) */

</script>

<style scoped>
    .color{
        border: 1px solid green;
    }
    .barre{
        text-decoration: line-through;
    }
    h1{
        text-align: center;
        color: #ddd;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 40px;
    }
    form{
        max-width: 75%;
        margin: 0 auto;
        border: 1px solid #eee;
        border-radius: 8px;
        padding: 35px;
    }
    label{
        display: block;
    }
    .to-do-list{
        max-width: 80%;
        margin: 0 auto;
    }
</style>


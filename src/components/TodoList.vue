<template>
    <div class="todo-list">
        <div>
          <input type="text" :value="inputValue" @input="setInput">
          <button @click="add">add</button>  
        </div>
        
        <list-item v-for="item in listData" :title="item" :checked="false" @onCheck="onCheck"></list-item>
    </div>
</template>
<script setup>
    import { ref } from 'vue';
import ListItem from './TodoList/ListItem.vue';
    const inputValue=ref('');
    const listData = ref([]);
    function setInput (e) {
        inputValue.value = e.target.value
        
    }
    function add () {
        if(inputValue.value.length>0) {
            listData.value.push(inputValue.value);
            inputValue.value=''
        }
    }
    const onCheck = (e) => {
        console.log(e)
    }
</script>
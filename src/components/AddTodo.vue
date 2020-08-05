<template>
    <div>
        <form @submit.prevent="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add an Item">
            <input type="submit" value="Add" class="btn">
        </form>
    </div>
</template>

<script>

//import uuid from 'uuid';
//import uuid from "vue-uuid";
//const { v4: uuidV4 } = require('uuid');

export default {
    name: 'AddTodo',
    data(){
        return {
            title: '',
        }
    },
    methods:{
        addTodo(){
            //e.preventDefualt();
            //let uid = todos.length;
            const newTodo = {
                //id: uuidV4(),
                title: this.title,
                completed: false,
            }
            //send to parent
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>




<style scoped>
form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
</style>
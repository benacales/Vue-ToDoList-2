<template>
  <div id="app">
    <div class = "home">
      <header>
      <b>My To-Do List</b>
      <p></p>
      </header>
      <todo-form @add = "addToDo">
      </todo-form>
      <todo-item v-for = "item in toDos" :item = "item" @remove="remove"></todo-item>
    </div>
  </div>
</template>

<script>

import Hello from './components/Hello.vue'
import listItem from './components/listItem.vue'
import TueDueForm from './components/TueDueForm.vue'

export default {
  name: 'app',
  components: {
    Hello,
    "todo-item": listItem,
    "todo-form": TueDueForm
  },
data() {
  return {
    toDos:[]
  }
},
methods : {
addToDo (value) {
    console.log(value)
    this.toDos.push(value)
    },
    remove(value) {
        const i = this.toDos.indexOf(value)
        this.toDos.splice(i, 1)
    }
  }
}
</script>
<style>
html {
    background-color : #717A8B;
    height : 100%;
    width : 100%;
}
header {
    background-color : blanchedalmond;
    height : 100%;
    width : 98.5%;
    border : solid;
    border-color : black;
    border-width : 3px;
    padding-top : -2em;
    padding-bottom : 1em;
    padding-left : 1.5em;
    margin-bottom : 1em;
}
b {
    font-size : 300%;
    padding-bottom : 2em;
}
.form {
    size : 200%;
}
.item {
    background-color : blanchedalmond;
    border : solid;
    border-color : black;
    border-width : 2px;
    font-size : 25px;
    padding : 3px;
    font-size : 160%;
    font-family : Georgia, 'Times New Roman', Times, serif;
    padding-left : 1em;
}
#theX {
    cursor : pointer;
    color : black;
}
#theX:hover {
    color: red;
}theBox {
    cursor : pointer;
}
#theCheck {
    cursor : pointer;
}
#inputTextBox {
    width : 25vw;
}
.checked {
    background-color : #80fcb2;
}
.notChecked {
    background-color : blanchedalmond;
}
</style>

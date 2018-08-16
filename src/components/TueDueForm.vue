<template>
<div class = "form">
    <input id = "inputTextBox" v-model = 'desc' type = "text" placeholder = "Enter in what you will end up procrastinating anyways">
    <button id = "theBox" @click = "add" type = "button"> Add </button>
    </div>
</template>
<script>
export default {
     data(){
        return{desc:""}
    }, 
    methods:{
        add() {
            this.$emit("add", this.desc); 
            this.desc = "";
        }
    }
}
</script>
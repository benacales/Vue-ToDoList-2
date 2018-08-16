<template>
<div class = "item" id = "colorChange" :class = "{checked : isClicked}">
    <span class = "task">{{item}}</span>
    <input type = "checkbox" @click= "doCheck()"/>
    <i @click = "remove" class = "fa fa-times" id = "theX">X</i>
    </div>
</template>
<script>
export default {
    props : [
        "item"
    ],
    data() {
        return {
            isClicked : false
        }
    },
    methods:{
        remove() {
            this.$emit("remove", this.item)
        },
        doCheck(item) {
            this.isClicked = !this.isClicked
        }
    }
}
</script>
<template>
   <h2>Hello World</h2>
   <h3>{{ text }}</h3>
   <button @click="changeText">Change Text</button>
</template>

<script>
export default {
    name: "Header",
    props: ["text"],
    data(){
        return{
            newText: "Text from Header.vue"
        }
    },
    methods: {
        changeText(){
            this.$emit("changeTitle", this.newText);
        }
    },
    emits: ["changeTitle"]
}
</script>

<style>
    
</style>
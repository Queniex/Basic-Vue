<template>
    <Header @changeTitle="changeText" :text="text"/>
</template>
  
<script>
    import Header from "@/components/Header.vue";

    export default {
        name: 'App',
            components:{
                Header
            },
        data(){
            return{
                text:"Text from App.vue"
            }
        },
        methods:{
            changeText(newText){
                this.text = newText;
            }
        }
    }
</script>
  
<style>

</style>
  
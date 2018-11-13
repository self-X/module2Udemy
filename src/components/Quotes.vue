<template>
    <div>
        <slot name="first-quote"></slot>
        <slot></slot> 
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
    .container {
        width: 250px;
        padding: 15px;
        border: 1px solid #ccc;
        box-shadow: 1px 1px 1px 1px #ccc;
        font-family: 'Arizonia', cursive;
        font-size: 26px;  
        text-align: center;
        word-wrap:  break-word;
    }

    #first-quote {
        margin: 100px 20px;
        height: 100%;
        float: left;
    }
    .other-quotes {
         float:  left;
         margin: 15px;
    }
</style>

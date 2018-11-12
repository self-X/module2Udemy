<template>
    <div class="new-quote">
        <div class="form-block">
            <p class="quote-paragraph">Quote</p>
            <form>
                <textarea class="quotesarea"></textarea>
                <br>
                <button class="btn btn-sm btn-primary add-quote">Add Quote</button>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
 .new-quote {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    align-content: center; 
    justify-content: center; 
    overflow: auto; 
 }
 .add-quote {
     margin-left: 250px;
 }
 .quote-paragraph {
     font-weight: 600;
     font-size:   14px;
 }
 .quotesarea{
     width: 600px;
     height: 80px;
 }
</style>

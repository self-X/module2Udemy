<template>
    <div class="container">
        <app-progress-bar></app-progress-bar>
        <br>
        <app-new-quote></app-new-quote>
        <app-quotes> 
            <div>
                <div slot="first-quote" id="first-quote" class="container">
                    {{ quoteStart }}          
                </div> 
            </div>
            <div> 
                <div class="container other-quotes"   
                    v-for = "slot in 9" 
                    :key = "slot"
                    :class = "{alert: activeQuote,  'alert-danger': activeQuote}"
                    :style = "{cursor: 'pointer'}"
                    @mouseover="onMouseOver"
                    @mouseleave="onMouseLeave">
                    {{ quoteStart }}          
                </div>  
            </div>
        </app-quotes>
        <app-info></app-info>
    </div>
</template>

<script>
    import ProgressBar from './components/Progress.vue';
    import NewQuote from './components/NewQuote.vue';
    import Quotes from './components/Quotes.vue';
    import Info from './components/Info.vue';
    export default {
        data() {
            return {
                quoteStart: 'Just a quote to start with something !',
                activeQuote: false,
            }
        },
        components: {
            appProgressBar: ProgressBar,
            appNewQuote: NewQuote,
            appQuotes: Quotes,
            appInfo: Info,
        },

        methods: {
            onMouseOver() {
                this.activeQuote = true;
            },
            onMouseLeave() {
                this.activeQuote = false;
            }
        }

    }
</script>

<style>
</style>

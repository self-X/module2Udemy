<template>
    <div class="container">
        <app-progress-bar :progress="progress"
        :total="total"></app-progress-bar>
        <br>
        <app-new-quote :quotes="quotes" @onNewQuote="addedQuoteProgress"></app-new-quote>
        <app-quotes> 
            <div>
                <div slot="first-quote" id="first-quote" class="container">
                    {{ quoteStart }}          
                </div> 
            </div>
            <div> 
                <div class="container other-quotes"   
                    v-for = "quote in quotes" 
                    :key = "slot">
                    {{ quote }}          
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
                quotes: [],
            }
        },

        computed: {
            progress(){                        
                return `${this.quotes.length * 10}%`; 
            },

            total(){
                return (this.quotes && this.quotes.length <= 10 && this.quotes.length) ||  
                (this.quotes.length >= 1 && this.quotes.length) || 0;
            }
        },

        components: {
            appProgressBar: ProgressBar,
            appNewQuote: NewQuote,
            appQuotes: Quotes,
            appInfo: Info,
        },
        
        watch: {
            total() {
                if (this.total > 10) {
                    this.total = 10;
                    this.progress = '100%';
                    alert('to many quotes');
                }
            }
        },

        methods: {
            addedQuoteProgress(quote) {
                this.quotes.push(quote);
            }
        }

    }
</script>

<style>
</style>

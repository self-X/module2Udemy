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
                    v-for = "(quote, index) in quotes" 
                    :key="`quote-${index}`"
                    @click="deleteQuote(index)">
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
                return `${((this.quotes && (this.quotes.length <= 10) && this.quotes.length) || 0 ) * 10}%`; 
            },

            total(){
                return (this.quotes && (this.quotes.length <= 10) && this.quotes.length) || 0;
            }
        },

        components: {
            appProgressBar: ProgressBar,
            appNewQuote: NewQuote,
            appQuotes: Quotes,
            appInfo: Info,
        },
        
        methods: {
            addedQuoteProgress(quote) {
                if (this.total < 10){ 
                    if(quote){
                        this.quotes.push(quote);
                    }
                } else {
                    alert('We are full of quotes');
                }     
            },

            deleteQuote(index){
                this.quotes = this.quotes.filter((el, key) => key != index );
            }
        }

    }
</script>

<style>
</style>

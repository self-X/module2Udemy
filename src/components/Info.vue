<template>
    <div>
        <div class="clear">
            <div class="alert alert-info quote-info-in-alert" role="alert">
                Info: {{ quoteInfo }}
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                quoteInfo: 'Click on a Quote to delete it.'
            }
        }
    }
</script>

<style>
    .clear{
        clear: left;
    }
    .quote-info-in-alert {
        text-align: center;
    }

</style>

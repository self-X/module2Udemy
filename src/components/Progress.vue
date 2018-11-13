<template>
    <div>
        <h1>Quotes Added</h1>
        <div class="progress">
            <div class="progress-bar" 
                role="progressbar" 
                :style="{width: progress}" 
                aria-valuenow="25" 
                aria-valuemin="0" 
                aria-valuemax="100">{{ total }}/10
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            progress: {
                type: String
            },
            total: {
                type: Number
            }
        },
    }
</script>

<style scoped>

</style>

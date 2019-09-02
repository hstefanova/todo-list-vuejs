<template>
    <div class="progressbar">
        <div class="progress-loader" :style="{width: (notes.length / counter )*100 + '%'}">{{ counter }} / {{ notes.length }}</div>
    </div>
</template>

<script>
    export default {
        props: ['counter', 'notes']
    }
</script>

<style scoped>
    .progressbar { background: #eee; width: 100%; height: 30px; }
    .progress-loader { width: 0; height: 100%; background: lightcoral; }
</style>
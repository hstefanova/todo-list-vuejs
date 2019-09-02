<template>
    <div>
        <slot></slot>

        <button @click="removeNote">X</button>
    </div>
</template>

<script>
    export default {
        data: function() {
           return {
               note: ''
           } 
        },
        methods: {
            removeNote() {
                this.$emit('noteWasDeleted', this.note)
            }
        }
    }
</script>

<style scoped>

</style>
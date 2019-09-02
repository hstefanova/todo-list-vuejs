<template>
    <div>
        <input type="text" v-model="note">
        <button @click.prevent="addNote">Add Note</button>
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
            addNote() {
                this.$emit('noteWasCreated', this.note)
                this.note = ''
            }
        }      
    }
</script>

<style scoped>

</style>
<template>
    <div>
        <Note 
            @noteWasDeleted="deleteNote" 
            v-for="note in notes">
            {{ note }}
        </Note>
    </div>
</template>

<script>
    import Note from './Note.vue'

    export default {
        props: ['notes'],
        components: {
            Note: Note
        },
        methods: {
            deleteNote(note) {
                this.notes.splice(note,1)
            }
        } 
    }
</script>

<style scoped>

</style>
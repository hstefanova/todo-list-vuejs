<template>
  <div id="app">
      <div class="wrapper">
        <div class="shell">
          <div class="content">
            <InputNote @noteWasCreated="addNote"></InputNote>

            <NoteList :notes="notes"></NoteList>

            <ProgressBar :notes="notes" :counter="counter"></ProgressBar>
          </div>
        </div>
      </div>
  </div>
</template>

<script>
import NoteList from './components/NoteList.vue'
import InputNote from './components/InputNote.vue'
import ProgressBar from './components/ProgressBar.vue'

export default {
  name: 'app',
  data: function() {
    return {
      notes: ['Default Note Goes Here'],
      counter: 5
    }
  },
  components: {
    NoteList: NoteList,
    InputNote: InputNote,
    ProgressBar: ProgressBar
  },
  methods: {
    addNote(note) {
      if(this.notes.length >= this.counter) {
        return alert('First, remove a note and then add a new one')
      }
      this.notes.push(note)
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .shell { max-width: 900px; margin: 0 auto; }

  .field { border: 2px solid lightblue; border-radius: 6px; padding: 10px; font-size: 15px; width: 400px; }
</style>

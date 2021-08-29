<template>
<div class="container">
   <Header @btn-click="toggleAddNote" :showAddNote="showAddNote"></Header>

   <div v-show="showAddNote">
     <AddNote @add-note = "addNote"></AddNote>
   </div>
   
  <Notes :notes="notes" @delete-note="deleteNote"></Notes>
</div>
  
</template>

<script>
  
import Header from './components/Header.vue'
import AddNote from './components/AddNote.vue'
import Notes from './components/Notes.vue'


  export default {
    name: 'App',
    components: {
       Header,
       AddNote,
       Notes
    },
    data() {
      return { 
        notes: [],
        showAddNote:false
      }
    },
    methods: {
      addNote(newNote) {
        this.notes = [ newNote,...this.notes, ]
      },    
      toggleAddNote() {
        this.showAddNote = !this.showAddNote
    },
    deleteNote(id) {
      this.notes = this.notes.filter((note) => note.id !==id)
    }
  }
  }
  
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn-block {
  display: inline-block;
  width: 30%;
}
.btn {
  display: inline-block;
  background: rgb(47, 3, 243);
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
</style>

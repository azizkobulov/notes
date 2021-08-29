<template>
<div :key="note.id" v-for="note in notes">
     <Note :note="note" @delete-note="$emit('delete-note', note.id)"></Note>
</div>
   
</template>

<script>
import Note from  './Note.vue'  
export default {
    name: 'Notes',
    props: {
        notes: Array
    },
    components: {
        Note
    },
    emits: ['delete-note']
}
</script>

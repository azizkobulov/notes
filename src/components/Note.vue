<template>
<div class="note">
    <div class="id">
    
        <i class="fas fa-times" @click="$emit('delete-note', note.id )"></i>
    </div>
    
    <h3>
        {{note.text}} 
    </h3>
    

    
</div>
    </template>
<script>
export default {
    name: 'Note',
    props: {
        note: Object, 
    }
}
</script>

<style scoped>
.fas {
   color: red; 
}
.note{
   background:#f4f4f4;
   margin: 5px;
   padding: 10px 20px;
   cursor: pointer;    
   }

.id {
    color: red;
    display: flex;
    justify-content:flex-end;
    }
.note h3 {
    margin-top: 50px;
    word-wrap:break-word;
}
</style>
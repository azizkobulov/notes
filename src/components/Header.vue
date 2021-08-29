<template>
   <div>
     <h1>NotePad</h1>
     <Button @btn-click="$emit('btn-click')"
     :text = "showAddNote ? 'Close' : 'Add Note'"
     ></Button>
    </div>
</template>
 
 <script>
    import Button from './Button.vue'

    export default {
        name: 'Header',
        props: {
            showAddNote: Boolean
        },
        components: {
            Button
        }
    }
</script>

<style scoped>
   div {
       display: flex;
       align-items: center;
       justify-content: space-between;
   }

</style>

<template>
    <button @click="onClick">{{text}}</button>
</template>

<script>
 export default {
     name: 'Button',
     methods: {
       onClick(){
         this.$emit('btn-click')
       }
     },
     props: {
       text: String
     }
 }
</script>

<style scoped>
button {
  display: inline-block;
  background: #000;
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
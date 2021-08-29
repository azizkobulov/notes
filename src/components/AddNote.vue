<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Note</label>
      <input type="text" v-model="text" name="text" placeholder="Add Note" autocomplete="off" />
    </div>

    <input type="submit" value="Save Note" class="btn btn-block" />
  </form>
</template>

<script>
export default {
    name: 'AddNote',
    data() {
      return {
        text: ''
      }
      
    },
    methods: {
      onSubmit(e) {
        e.preventDefault()

        if(!this.text) {
          alert('Please add a note')
          return 
        }
        let newNote = {
          id: Math.floor((Math.random() * 100000)/1000),
          text: this.text
        }
         this.$emit('add-note', newNote)
         this.text= ''
         
      }
    }
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
  font-size: 30px;
}
.form-control input {
  width: 70%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
</style>
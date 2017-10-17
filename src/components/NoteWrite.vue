<template>
  <div>
      <form>
          <div class="form-group">
                <label for="title" action="submit"> Note Title</label>
                <input type="text" id="title" v-model="note.title" class="form-control">
          </div>
          <div class="form-group">
                <label for="textInput" class="pull-left"> Note Text</label>
                <textarea name="textInput" id="textInput" cols="30" rows="4" v-model="note.textInput" class="form-control"></textarea>
          </div>
          <button class="btn btn-primary" @click.prevent="submit">Submit</button>
      </form>
  </div>
</template>

<script>
import { noteBus } from '../main';
export default {
    data() {
        return{
            note: {
                title: '',
                textInput: ''
            },
            notes: []
        }
    },
    methods: {
        submit() {
            let text, title;
            text = this.note.textInput;
            title = this.note.title;
            // let {textInput, title} = this.note;
            //this.notes.push({textInput, title, date: new Date(Date.now()).toLocaleDateString()});
            noteBus.$emit('newNote', title, text);
            this.note.textInput = '';
            this.note.title ='';
        }
    }
}
</script>

<style>

</style>

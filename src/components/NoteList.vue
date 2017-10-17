<template>
  <div class="row">
      <div  v-for="(note,index) in notes" :key="index">
          <app-note :note="note"  @click="removeNote(index)"></app-note>
      </div>
      
  </div>
</template>

<script>
import { noteBus } from '../main';
import Note from './Note.vue';
export default {
    data() {
        return {
            note: {
                title: '',
                textInput: '',
                date: Date(),
                id: ''
            },
            notes: []
        }
    },
    created() {
        noteBus.$on('newNote', (title, text) => {
            this.note.title = title;
            this.note.textInput = text;
            this.note.date = new Date(Date.now()).toLocaleDateString();
            this.note.id = new Date(Date.now()).getTime();
            this.notes.push(this.note);
            console.log(this.notes);
        })
    },
    components:{
        appNote: Note
    },
    // methods:{
    //     removeNote(index){
    //         noteBus.$on('removeNote',(index) => {
    //             console.log(index);
    //         })
    //         this.notes.splice(this.note.index, 1);
    //     }
    // }
}
</script>

<style>

</style>

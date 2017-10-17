<template>
  <div id="app" class="container">
    <h1 class="appName">{{ msg }}</h1>
    <app-note-write></app-note-write>
    <hr>
    <app-note-list></app-note-list>
  </div>
</template>

<script>
import NoteWrite from './components/NoteWrite.vue';
import NoteList from './components/NoteList.vue';
export default {
  name: 'app',
  data () {
    return {
      msg: 'Notemaster in Vue JS'
    }
  },
  components: {
    appNoteWrite: NoteWrite,
    appNoteList: NoteList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
.appName{
  text-align:center;
}

</style>

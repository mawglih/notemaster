<template>
<div>
    <div class="note">
    <div class="card">
        <div class="card-header bg-primary text-white">
            <h4 class="card-title">{{note.title}}</h4>
            
        </div>
        <div class="card-block size">
            
            <p class="card-text">{{note.textInput}}</p>
        </div>
        <div class="card-footer bg-info text-white">
            {{note.date}}
        </div>
    </div>
    <button class="btn btn-danger float-right"  >Remove Note</button>
</div>
</div>

    
</template>

<script>
import { noteBus } from '../main';
export default {
    props: ['note']
    // methods: {
    //     removeNote(index) {
    //         // if(this.index === index) {
    //         //     noteBus.$emit('removeNote', index);
    //         // }
    //     }
    // }
}
</script>

<style>
.note{
    
    margin: 10px;
}
.size {
    min-height: 100px;
}

</style>

<template>
<div>
    <div class="note">
    <div class="card">
        <div class="card-header">
            <h4 class="card-title">{{note.title}}</h4>
            
        </div>
        <div class="card-block">
            
            <p class="card-text">{{note.textInput}}</p>
        </div>
        <div class="card-footer">
            {{note.date}}
        </div>
    </div>
</div>
</div>

    
</template>

<script>
export default {
    props: ['note']
}
</script>

<style>
.note{
    
    margin: 10px;
}

</style>

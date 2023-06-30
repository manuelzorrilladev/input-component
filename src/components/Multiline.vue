<script setup>
    const {row} = defineProps(['row'])
</script>

<template>
    <div class="input">
        <label for="multiline">Multiline rows={{row}}</label>
        <br>
        <textarea name="multiline" cols="30" :rows="row" placeholder="Placeholder"></textarea>
    </div>
</template>

<style scoped>
textarea{
    max-width: 180px;
    padding: 20px 10px;
    resize: none;
    height: fit-content;
    border-radius: 10px;
}
</style>
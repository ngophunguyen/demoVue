<template>
    <div class="parent">
        <h3>Parent 1</h3>
        <button type="button" @click="$emit('openPopup', {value: 1, text: 'Data parent 1 popup 1'})" class="button">Popup 1</button>
        <button type="button" @click="$emit('openPopup', {value: 2, text: 'Data parent 1 popup 2'})" class="button">Popup 2</button>
    </div>
</template>
<script>

export default {
    name: 'Parent 1',
    setup() {
        return {
            
        }
    },
}
</script>
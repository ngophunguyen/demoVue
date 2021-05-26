<template>
    <div class="parent">
        <h3>Parent 2</h3>
        <button type="button" @click="$emit('openPopup', {value: 1, text: 'Data parent 2 popup 1'})" class="button">Popup 1</button>
        <button type="button" @click="$emit('openPopup', {value: 2, text: 'Data parent 2 popup 2'})" class="button">Popup 2</button>
        <button type="button" @click="$emit('openPopup', {value: 3, text: 'Data parent 2 popup 3'})" class="button">Popup 3</button>
    </div>
</template>
<script>

export default {
    name: 'Parent 2',
    setup() {
        return {
            
        }
    },
}
</script>
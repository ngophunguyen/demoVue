<template>
    <div class="background" v-if="isVisible" @click="close"></div>
    <transition name="fade" v-if="isVisible">
        <div class="popup">
            <div id="popup1" class="box-popup">
                <h3>Popup 2</h3>
                <p>{{ msg }}</p>
            </div>
        </div>
    </transition>
</template>
<script>
import { ref } from 'vue'
export default {
    name: 'Popup 2',
    props: {
        msg: String,
    },
    setup() {
        let isVisible = ref(false);
        const open = () => {
            isVisible.value = true
        };
        const close = () => {
            isVisible.value = false
        };
        return {
            isVisible,
            open,
            close
        }
    }
}
</script>
<style scoped>
    
</style>
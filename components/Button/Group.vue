
<template>
    <ul ref="buttonGroup" class="button-group" tabindex="0">
        <li v-for="(item, index) in count" :key="`button-group-item-${index}`">
            <slot :name="`button-${index}`">
            </slot>
        </li>
    </ul>
</template>

<script setup>
import { ref, onMounted } from 'vue';
const props = defineProps({
    count: {
        type: Number,
        required: true,
    }
})
</script>

<style scoped lang='scss'>
.button-group{
    width: fit-content;
    display: flex;
    gap: 10px;
    justify-content: flex-start;
    align-items: center;
}
</style>
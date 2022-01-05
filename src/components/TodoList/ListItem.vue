<template>
    <label>
        {{title}}
        <input type="checkbox" :value="checked" @click="click">
    </label>
</template>
<script setup>
    const props = defineProps({
        title: {
            type: String,
            default: ''
        },
        checked: {
            type: Boolean,
            default: false
        }
    })
    const emit = defineEmits([
        'onCheck'
    ])
    const click = (e) => {
        emit('onCheck', e);
    }
</script>
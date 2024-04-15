<template>
    <component :is="tag">

    </component>
</template>


<script setup>
    import { defineProps } from 'vue';
    import { bool, string } from 'vue-types';



    const props = defineProps({
        tag:string(),
        icon:string(),
        isIconOnly:bool().def(false)
    })
</script>
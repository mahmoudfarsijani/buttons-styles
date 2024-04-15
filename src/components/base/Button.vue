<template>
    <component :is="tag" :class="['button']">
        <slot v-if="!isIconOnly"/>
        <Icon v-if="icon" :name="icon"/>
    </component>
</template>


<script setup>
    import { defineProps,computed } from 'vue';
    import { bool, string } from 'vue-types';

    import Icon from '@/components/base/Icon.vue'



    const props = defineProps({
        tag:string(),
        icon:string(),
        isIconOnly:bool().def(false),
        isPill:bool().def(false),
        isCircle:bool().def(false),
        isPrimary:bool().def(false),
        isSuccess:bool().def(false),
        isInfo:bool().def(false),
        isWarning:bool().def(false),
        isDanger:bool().def(false),
        isSharp:bool().def(false),
        isSoft:bool().def(false),
        isBorder:bool().def(false),
        isTransparent:bool().def(false),
        isCapitalize:bool().def(false)

    })

    const elementClass = computed(() => ({
        'is-pill': props.isPill,
        'is-circle': props.isCircle,
        'is-primary': props.isPrimary,
        'is-success': props.isSuccess,
        'is-info': props.isInfo,
        'is-warning': props.isWarning,
        'is-danger': props.isDanger,
        'is-sharp': props.isSharp,
        'is-soft': props.isSoft,
        'is-border': props.isBorder,
        'is-transparent': props.isTransparent,
        'is-capitalize': props.isCapitalize
    }))
</script>
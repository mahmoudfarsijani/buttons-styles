<template>
    <component :is="tag" :class="['button',elementClass]">
        <slot v-if="!isIconOnly"/>
        <Icon v-if="icon" :name="icon"/>
    </component>
</template>


<script setup>
    import { defineProps,computed } from 'vue';
    import { bool, oneOf, string } from 'vue-types';

    import Icon from '@/components/base/Icon.vue'



    const props = defineProps({
        tag:oneOf(['button','a','span','router-link']).def('button'),
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
        isCapitalize:bool().def(false),
        isBorderPrimary:bool().def(false),
        isBorderDanger:bool().def(false),
        isBorderWarning:bool().def(false),
        isBorderSuccess:bool().def(false),
        isBorderInfo:bool().def(false)

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
        'is-capitalize': props.isCapitalize,
        'is-border-danger': props.isBorderDanger,
        'is-border-warning': props.isBorderWarning,
        'is-border-success': props.isBorderSuccess,
        'is-border-info': props.isBorderInfo,
        'is-border-primary': props.isBorderPrimary
    }))
</script>


<style scoped>
    .button {
        @apply cursor-pointer p-[8px]
    }

    .button.is-pill {
        @apply px-[50px] flex flex-nowrap rounded-full items-center
    }

    .button.is-circle {
        @apply rounded-full
    }

    .button.is-primary {
        @apply bg-blue-500
    }

    .button.is-success {
        @apply bg-lime-500
    }

    .button.is-info {
        @apply bg-sky-400
    }

    .button.is-warning {
        @apply bg-yellow-300
    }

    .button.is-danger {
        @apply bg-red-500
    }

    .button.is-sharp {
        @apply rounded-none
    }

    .button.is-soft { 
        @apply rounded-md
    }

    .button.is-border {
        @apply border-black border-2
    }

    .button.is-transparetnt {
        @apply bg-transparent
    }

    .button.is-capitalize {
        @apply capitalize
    }

    .button.is-border-danger {
        @apply border-red-500 border-2
    }

    .button.is-border-success {
        @apply border-lime-500 border-2
    }

    .button.is-border-warning {
        @apply border-yellow-300 border-2
    }

    .button.is-border-info {
        @apply border-sky-400 border-2
    }

    .button.is-border-primary {
        @apply border-blue-500 border-2
    }

   

    
</style>
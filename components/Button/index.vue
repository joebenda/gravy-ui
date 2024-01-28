<template>
    <div>
        <component 
            :is="!link ? 'button' : 'a'"
            :type="type" 
            :aria-label="label"
            :class="[`${variant}-button`]"
            :disabled="disabled"
            :href="link"
            :target="externalLink ? '_blank' : ''"
        >
            <slot />
    </component>
    </div>
</template>

<script setup>

/**
 * TODO;
 * icon
 * icononly
 * shape : circle, square
 * sizes
 * hover tooltips
 * flash on load
 * 
 */

const props = defineProps({

    label: {
        type: String,
        required: true,
    },
    variant: {
        type: String,
        default: 'primary',
        validator(value) {
            return ['primary', 'secondary'].includes(value);
        }
    },
    type: {
        type: String,
        default: 'button',
        validator(value) {
            return ['button', 'submit', 'reset'].includes(value);
        }
    },
    link: {
        type: String,
        required: false
    },
    externalLink: {
        type: Boolean,
        default: false,
    },
    disabled: {
        type: Boolean,
        default: false,
    }
})
</script>

<style scoped lang='scss'>
button, a{
    
    padding: $spacing-two;
    border-radius: $spacing-one;
    border: none;
    text-decoration: none;
    display: inline-block;
    cursor: pointer;

    &:focus-visible{
        outline: $accessible-outline;
    }

    &.primary-button {
        background-color: $primary;
        color: $contrast-color;
    }

    &.secondary-button {
        background-color: $secondary;
        color: $contrast-color;
    }

    &:disabled{
        background-color: $disabled;
        cursor: not-allowed;
    }
}

</style>
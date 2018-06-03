<template>
    <button
        :aria-pressed="toggled.toString()"
        class="toggle-switch"
        @click="toggled = !toggled"
    >
        <div class="rail">
            <div :class="['switch', { toggled }]"/>
        </div>

        <span :class="['label-text', { 'text-muted': !toggled }]">
            <slot/>
        </span>
    </button>
</template>

<script>
    export default {
        name: 'ToggleSwitch',
        data: () => ({
            toggled: false
        }),
        computed: {
            idPrefix() {
                return `${this.$vnode.tag.toLowerCase()}__`;
            }
        }
    };
</script>

<style lang="sass" scoped>
    $toggled-color: #00a3d9

    @keyframes glow
        0%
            text-shadow: 0 0 8px rgba($color: lighten($toggled-color, 25%), $alpha: .25)

        50%
            text-shadow: 18px 18px 40px rgba($color: lighten($toggled-color, 30%), $alpha: .4)

        100%
            text-shadow: 0 0 8px rgba($color: lighten($toggled-color, 25%), $alpha: .25)

    .label-text
        text-indent: .5rem

        &:not(.text-muted)
            animation-duration: .25s
            animation-name: glow

    .rail
        align-items: center
        background-color: #ddd
        border-radius: .25rem
        display: flex
        height: .65rem;
        position: relative
        top: .1rem
        user-select: none
        width: 2rem

    .switch
        background-color: #adadad
        border-radius: 100%
        height: 1rem;
        left: 0
        position: absolute
        transform: translateX(0)
        transition: all 0.2s ease-in-out
        width: 1rem

        &.toggled
            background-color: $toggled-color
            transform: translateX(1rem)

    .text-muted
        color: #6c757d

    .toggle-switch
        align-items: center
        background-color: rgba($color: #000000, $alpha: 0)
        border: 0
        display: flex
        font-size: 1.5rem
</style>

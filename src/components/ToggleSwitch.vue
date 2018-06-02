<template>
    <div class="toggle-switch">
        <label>
            <input v-model="checked" type="checkbox">
            <div class="rail">
                <div :class="['circle', { checked }]"/>
            </div>
            <span class="label-text"><slot/></span>
        </label>
    </div>
</template>

<script>
    export default {
        name: 'ToggleSwitch',
        data: () => ({
            checked: false
        })
    };
</script>

<style lang="scss" scoped>
    %circle {
        background-color: #adadad;
        border-radius: 100%;
        content: '';
        height: 15px;
        left: 0;
        position: absolute;
        top: -3px;
        transform: translateX(0);
        transition: all 0.2s ease-in-out;
        width: 15px;
    }

    %rail {
        background-color: #ddd;
        border-radius: 4px;
        height: 10px;
        margin: 20px 0;
        position: relative;
        user-select: none;
        width: 32px;
    }

    input[type='checkbox'] {
        visibility: hidden;
    }

    label {
        // @extend %rail;
        align-items: center;
        display: flex;

        // &::after {
        //     @extend %circle;
        // }
    }

    .circle {
        @extend %circle;

        &.checked {
            background-color: #00A3D9;
            transform: translateX(17px);
        }
    }

    .rail {
        @extend %rail;
    }

    // .label-text {

    // }

    // .toggle-switch {
    //     align-items: center;
    //     display: flex;
    // }
</style>

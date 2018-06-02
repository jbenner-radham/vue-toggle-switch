<template>
    <label class="toggle-switch">
        <input v-model="toggled" type="checkbox">
        <div class="rail">
            <div :class="['switch', { toggled }]"/>
        </div>
        <span class="label-text"><slot/></span>
    </label>
</template>

<script>
    export default {
        name: 'ToggleSwitch',
        data: () => ({
            toggled: false
        })
    };
</script>

<style lang="scss" scoped>
    input[type='checkbox'] {
        visibility: hidden;
    }

    .label-text {
        text-indent: .5rem;
    }

    .rail {
        background-color: #ddd;
        border-radius: 4px;
        height: 10px;
        margin: 20px 0;
        position: relative;
        user-select: none;
        width: 32px;
    }

    .switch {
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

        &.toggled {
            background-color: #00A3D9;
            transform: translateX(17px);
        }
    }

    .toggle-switch {
        align-items: center;
        display: flex;
    }
</style>

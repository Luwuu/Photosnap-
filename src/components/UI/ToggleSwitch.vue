<template>
    <div class="toggle-switch">
        <p>Monthly</p>
        <label class="switch">
            <input type="checkbox" @click="toggleSwitch" />
            <span class="slider round"></span>
        </label>
        <p>Yearly</p>
    </div>
</template>

<script>
export default {
    emits: ['togglePrices'],
    methods: {
        toggleSwitch() {
            this.$emit('togglePrices')
        },
    },
}
</script>

<style lang="scss" scoped>
.toggle-switch {
    width: 100%;
    font-size: 2rem;
    display: flex;
    justify-content: center;
    margin-bottom: 2rem;
}
/* The switch - the box around the slider */
.switch {
    margin: 0 1rem;
    position: relative;
    display: inline-block;
    width: 60px;
    height: 34px;
}

/* Hide default HTML checkbox */
.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}

/* The slider */
.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    -webkit-transition: 0.4s;
    transition: 0.4s;
}

.slider:before {
    position: absolute;
    content: '';
    height: 26px;
    width: 26px;
    left: 4px;
    bottom: 4px;
    background-color: black;
    -webkit-transition: 0.4s;
    transition: 0.4s;
}
input:checked + .slider:before {
    background-color: white;
}

input:checked + .slider {
    background-color: black;
}

input:focus + .slider {
    box-shadow: 0 0 1px black;
}

input:checked + .slider:before {
    transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
    border-radius: 34px;
}

.slider.round:before {
    border-radius: 50%;
}
</style>

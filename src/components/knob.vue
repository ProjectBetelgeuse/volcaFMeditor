<template>
    <div class="column q-gutter-md">
        <div class="col">
            <div class="knob" :style="{ cursor: pointer }" ref="knob">
                <div :style="{ transform: 'rotate(' + turn + 'deg)' }" class="turning">
                    <div class="handle"
                        :style="handleStyle">
                    </div>
                    <div class="inner"
                        :style="innerStyle">
                    </div>
                </div>
            </div>
        </div>
        <div class="col">
            <input class="digits" type="text" v-model.number="value" onfocus="value = ''"
                @focusout="changeCurrentValue()" @input="limit()">
        </div>
    </div>
</template>
<script lang="ts" setup>
import { computed, reactive, ref } from 'vue';
import { usePointerSwipe } from '@vueuse/core';
const knob = ref<HTMLElement | null>(null);
var turn = computed(() => {
    return value.value * 2.7 - 135;
});
var value = ref(0)
var currentValue = ref(0);
var pointer = ref('grab');
const { distanceX } = usePointerSwipe(knob, {
    onSwipeStart: () => {
        pointer.value = 'grabbing';
    },
    onSwipe: (e: PointerEvent) => {
        value.value = Math.round(currentValue.value - distanceX.value * 0.5);
        if (value.value > 100) {
            value.value = 100
        } else if (value.value < 0) {
            value.value = 0
        }
    },
    onSwipeEnd: (e: PointerEvent) => {
        currentValue.value = value.value;
        pointer.value = 'grab';
    },
    threshold: 1
});
function changeCurrentValue() {
    currentValue.value = value.value;
}
function limit() {
    if (value.value > 100) {
        value.value = 100
    } else if (value.value < 0) {
        value.value = 0
    }
}
const handleStyle = reactive({
    'box-shadow': 'inset 2px 0px 3px #7b3210, inset -2px 0px 3px #f18d3b'
});
const innerStyle = reactive({
    'box-shadow': 'inset 4px 0px 6px #7b3210, inset -4px 0px 6px #f18d3b'
})
</script>
<style scoped>
@font-face {
    font-family: Digital-7;
    src: url('../font/digital-7.ttf');
}

.digits {
    width: 30px;
    height: 20px;
    border-radius: 5px;
    display: flex;
    margin: auto;
    font-family: Digital-7;
    background: #b1b0b2;
    box-shadow: 4px 4px 9px #a3a2a4,
        -4px -4px 9px #bfbec0;
    border: 0;
    outline: 0;
    text-align: center;
}

.digits:focus {
    outline: none !important
}

.turning {
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.2s;
}

.knob {
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: #b1b0b2;
    box-shadow: 4px 4px 9px #989799,
        -4px -4px 9px #cac9cb;
    overflow: hidden;
}

.handle {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: -36px;
    width: 7px;
    height: 15px;
    background: #f56320;
}

.inner {
    position: relative;
    width: 24px;
    height: 24px;
    border-radius: 93px;
    background: #f56320;
    border-color: #b1b0b2;
    /* box-shadow: inset 3px 0px 4px #722f10,
        inset -3px 0px 4px #ff7433; */

}
</style>
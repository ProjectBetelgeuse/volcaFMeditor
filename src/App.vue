<template>
    <div class="q-pa-md">
        <div class="column">
            <div class="col">
                <div class="row">
                    <div class="col q-gutter-sm">
                        <midiDeviceSelectVue></midiDeviceSelectVue>
                        <FileLoadSave></FileLoadSave>
                    </div>
                    <div class="col q-gutter-sm">
                        <Algorithm></Algorithm>
                    </div>
                    <div class="col q-gutter-sm">
                        <waveDisplay></waveDisplay>
                    </div>
                </div>
            </div>
            <div class="col">
                <Operator></Operator>
            </div>
        </div>
    </div>

</template>

<script lang="ts" setup>
import midiDeviceSelectVue from './components/midiDeviceSelect.vue';
import FileLoadSave from './components/fileLoadSave.vue';
import Operator from './components/Operator.vue';
import waveDisplay from './components/waveDisplay.vue';
import Algorithm from './components/algorithm.vue';

</script>

<style>
body {
    background-color: white;
}
</style>
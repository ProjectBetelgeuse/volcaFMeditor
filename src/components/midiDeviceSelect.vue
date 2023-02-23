<template>
  <q-card class="my-card">
    <q-card-section>
      <div class="text-h6">MiDi Device Setup</div>
    </q-card-section>
    <q-separator></q-separator>
    <q-card-actions vertical>
      <div class="column q-gutter-sm">
        <div class="text-h6 col">Select Midi Device</div>
        <div class="col">
          <q-select outlined dense v-model="midiDevice" :options="midiDevices" label="Midi Device"></q-select>
        </div>
        <div class="text-h6 col">Select Midi Channel</div>
        <div class="col">
          <q-select outlined dense v-model="midiChannel" :options="midiChannels" label="Midi Channel"></q-select>
        </div>
      </div>
    </q-card-actions>
  </q-card>
</template>
<script lang="ts" setup>
import { ref } from 'vue';

var midiChannels: number[] = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16];
var midiChannel = ref(1);

</script>

<style>
</style>
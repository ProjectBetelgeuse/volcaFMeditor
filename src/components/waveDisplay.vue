<template>
<q-card>
        <q-card-section>
      <div class="text-h6">Wave</div>
    </q-card-section>
     <q-separator></q-separator>
     <q-card-section> 
        <canvas id="waveCanvas" ref="waveCanvas"></canvas>
    </q-card-section>
</q-card>
</template>

<script setup lang="ts">
import { ref,onMounted } from "vue";
import makeEnvelope from "./waveDisplay.js"

const waveCanvas = ref(null)
onMounted(() => {
    makeEnvelope('52', '6', '0', '80', '99', '0', '0', '0', waveCanvas.value);
})

</script>
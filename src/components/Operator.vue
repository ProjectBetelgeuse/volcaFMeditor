<template>
    <q-card>
        <q-card-section>
            <div class="text-h6">Operator</div>
        </q-card-section>
        <q-separator></q-separator>
        <q-card-section style="background-color: #b1b0b2;">
                <div class="column q-gutter-md">
                    <div class="col">
                        <div class="row">
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <q-separator vertical inset />
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                        </div>
                    </div>
                    <q-separator inset />
                    <div class="col">
                        <div class="row">
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <q-separator vertical inset />
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                            <div class="col">
                                <knob></knob>
                            </div>
                        </div>
                    </div>
                </div>
        </q-card-section>
    </q-card>

</template>

<script lang="ts" setup>
import knob from './knob.vue';


</script>
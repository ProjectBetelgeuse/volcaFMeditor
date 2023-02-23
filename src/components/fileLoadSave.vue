<template>
  <q-card>
    <q-card-section>
      <div class="text-h6">Save/Load/Share</div>
    </q-card-section>

    <q-separator></q-separator>

    <q-card-actions vertical>
      <div class="column q-gutter-sm">
        <div class="col">
          <q-file outlined dense v-model="fileUpload" label="Upload File" class="full-width">
            <template v-slot:prepend>
              <q-icon name="attach_file" />
            </template>
            <template v-slot:append>
              <q-icon name="close" @click.stop="fileUpload = null" class="cursor-pointer" />
            </template>
          </q-file>
        </div>
        <div class="col">
          <q-btn outline icon="save" color="primary" label="Save File" class="full-width" />
        </div>
        <div class="col">
          <q-btn outline icon="share" color="primary" label="Create Sharable Patch Link" class="full-width" />
        </div>
      </div>
    </q-card-actions>

  </q-card>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
var fileUpload = ref(null);
</script>

<style>
</style>
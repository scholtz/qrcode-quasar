<template>
  <q-page class="column items-center justify-evenly">
    <div>
      <h1>Qasar qrcode-vue3 demo app</h1>
      <div>
        Npm package:
        <a href="https://www.npmjs.com/package/qrcode-vue3">qrcode-vue3</a>
      </div>
      <div>
        Source code:
        <a href="https://github.com/scholtz/qrcode-vue3">GitHub</a>
      </div>
    </div>
    <QRCodeVue3
      :width="400"
      :height="400"
      :value="data"
      :key="data"
      :qr-options="{ errorCorrectionLevel: 'H' }"
      :image-options="{ hideBackgroundDots: true, imageSize: 0.4, margin: 10 }"
      :corners-square-options="{ type: 'dot', color: '#2D79C5' }"
      :corners-dot-options="{ type: undefined, color: '#2D79C5' }"
      :dots-options="{
        type: 'dots',
        color: '#2D79C5',
        gradient: {
          type: 'linear',
          rotation: 0,
          colorStops: [
            { offset: 0, color: '#3998F7' },
            { offset: 1, color: '#24619E' },
          ],
        },
      }"
      image="usdc.svg"
      :download="false"
    />
    <q-input v-model="data" label="Data in QRCode" class="full-width q-pa-lg" />
    {{ data }}
  </q-page>
</template>

<script setup lang="ts">
import QRCodeVue3 from 'qrcode-vue3';
import { ref } from 'vue';

const data = ref<string>(
  'algorand://ALGONAUTSPIUHDCX3SLFXOFDUKOE4VY36XV4JX2JHQTWJNKVBKPEBQACRY?amount=10000000&note=Quasar&label=Quasar&asset=31566704'
);
</script>

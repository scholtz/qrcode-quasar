<template>
  <q-page class="column items-center justify-evenly">
    <div>
      <h1>Quasar qrcode-vue3 demo app</h1>
      <div>
        Npm package:
        <a href="https://www.npmjs.com/package/qrcode-vue3">qrcode-vue3</a>
      </div>
      <div>
        QRCode library source code:
        <a href="https://github.com/scholtz/qrcode-vue3"
          >https://github.com/scholtz/qrcode-vue3</a
        >
      </div>
      <div>
        This app source code:
        <a href="https://github.com/scholtz/qrcode-quasar/"
          >https://github.com/scholtz/qrcode-quasar/</a
        >
      </div>
    </div>
    <q-input v-model="image" label="Image" class="full-width q-pa-lg" />
    <q-input v-model="data" label="Data in QRCode" class="full-width q-pa-lg" />
    <q-input v-model="c1" label="Color 1" class="full-width q-pa-lg" />
    <q-input v-model="c2" label="Color 2" class="full-width q-pa-lg" />
    <q-input v-model="c3" label="Color 3" class="full-width q-pa-lg" />
    {{ data }}
    <div style="height: 500px">
      <QRCodeVue3
        :width="400"
        :height="400"
        :value="data"
        :key="data"
        :qr-options="{ errorCorrectionLevel: 'H' }"
        :image-options="{
          hideBackgroundDots: true,
          imageSize: 0.4,
          margin: 10,
        }"
        :corners-square-options="{ type: 'dot', color: c1 }"
        :corners-dot-options="{ type: undefined, color: c1 }"
        :dots-options="{
          type: 'dots',
          color: c1,
          gradient: {
            type: 'linear',
            rotation: 0,
            colorStops: [
              { offset: 0, color: c2 },
              { offset: 1, color: c3 },
            ],
          },
        }"
        :image="image"
        :download="false"
      />
    </div>
  </q-page>
</template>

<script setup lang="ts">
import QRCodeVue3 from 'qrcode-vue3';
import { ref } from 'vue';

const data = ref<string>(
  'algorand://ALGONAUTSPIUHDCX3SLFXOFDUKOE4VY36XV4JX2JHQTWJNKVBKPEBQACRY?amount=10000000&note=Quasar&label=Quasar&asset=31566704'
);
const image = ref<string>('usdc.svg');
const c1 = ref<string>('#2D79C5');
const c2 = ref<string>('#3998F7');
const c3 = ref<string>('#24619E');
</script>

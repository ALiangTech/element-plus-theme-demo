<template>
    <section>
      <div>浏览器指纹:{{ user.uuid }}</div>
      <div>
        <div v-for="[key, value] of user.result">
          <b>{{ key }}</b
          >:<span>{{ value }}</span>
        </div>
      </div>
    </section>
  </template>
  <script setup>
    import {reactive} from 'vue'
    import FingerprintJS from '@fingerprintjs/fingerprintjs';
    const user = reactive({
      uuid: '',
      result: null,
    });
    // Initialize an agent at application startup.
    const fpPromise = FingerprintJS.load();
  
    (async () => {
      // Get the visitor identifier when you need it.
      const fp = await fpPromise;
      const result = await fp.get();
      console.log(result.visitorId);
      user.uuid = result.visitorId;
      user.result = Object.entries(result);
    })();
  </script>
  <style scoped>
    div {
      padding: 10px;
    }
  </style>
  
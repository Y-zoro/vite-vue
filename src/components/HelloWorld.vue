<template>
  <div class="label">{{ msg }}</div>
  <hr />
  <p class="label">
    <van-checkbox type="checkbox" v-model="useScriptSetup"> Use<code>&lt;script setup&gt;</code></van-checkbox>
  </p>
  <hr />
  <p class="label">
    <van-checkbox type="checkbox" v-model="useTsPlugin"> Provide types for<code>*.vue</code> imports</van-checkbox>
  </p>
  <hr />
  <p class="label">
    Recommended IDE setup:
    <a href="https://code.visualstudio.com/" target="_blank">VSCode</a>
    +
    <template v-if="!useScriptSetup">
      <a
        href="https://marketplace.visualstudio.com/items?itemName=octref.vetur"
        target="_blank"
      >Vetur</a>
      +
      <a
        href="https://marketplace.visualstudio.com/items?itemName=znck.vue-language-features"
        target="_blank"
      >Vue DX</a>
    </template>
    <template v-else>
      <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    </template>
  </p>
  <p class="label" v-if="useTsPlugin">
    tsconfig setup:
    <br />1. Install and add
    <code>@vuedx/typescript-plugin-vue</code> to tsconfig plugins
    <br />2. Delete <code>src/shims-vue.d.ts</code>
    <br />3. Open
    <code>src/main.ts</code> in VSCode
    <br />4. Open VSCode command input
    <br />5. Search and run "Select TypeScript version" -> "Use workspace version"
  </p>
  <van-button type="primary" @click="count++">count is: {{ count }}</van-button>
  <p class="label">
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>

  <p class="label" >
    <a href="https://vitejs.dev/guide/features.html" target="_blank">Vite Docs</a> |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Docs</a>
  </p>
</template>

<script lang="ts">
import { ref, defineComponent } from 'vue'
export default defineComponent({
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      required: true
    }
  },
  setup: () => {
    const count = ref(0)
    const useScriptSetup = ref(false);
    const useTsPlugin = ref(false);
    return { count, useScriptSetup, useTsPlugin }
  }
})
</script>

<style scoped>
a {
  color: #42b983;
}
.label {
  margin: 0 0.5em;
  font-weight: bold;
  font-size: 16px;
  line-height: 2;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
  font-size: 16px;
}
</style>

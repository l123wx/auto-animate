# Auto-animate

https://github.com/formkit/auto-animate

使用很少的代码，就能给页面加上动画

## 用法（vue）

全局添加：

main.ts
```ts
import { createApp } from 'vue'
import App from './App.vue'
import { autoAnimatePlugin } from '@formkit/auto-animate/vue'

createApp(App).use(autoAnimatePlugin).mount('#app')
```

注册插件之后，直接使用 `v-auto-animate` 属性就可以开启动画

App.vue
```vue
<script setup>
import { ref } from 'vue'
const items = ref(["😏","😐","😑","😒","😕", ... ])
function removeItem(toRemove) {
  items.value = items.value.filter((item) => item !== toRemove)
}
</script>

<template>
  <h5>Click emojis to remove them.</h5>
  <ul v-auto-animate>
    <li
      v-for="item in items"
      :key="item"
      @click="removeItem(item)"
    >
      {{ item }}
    </li>
  </ul>
</template>
```

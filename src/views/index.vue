<template>
  <div>
    <h1>GitHub Pages Starter</h1>
    
    <ul v-auto-animate>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>

    <button @click="handleClick">Add Items</button>

    <div v-auto-animate>
      <h1>This is a title</h1>
      <p v-if="isContentShow">This is a very long content. This is a very long content. This is a very long content. This is a very long content. This is a very long content. This is a very long content.</p>
    </div>

    <button @click="handleContentShowClick">Show Content</button>
  </div>
</template>


<script setup lang="ts">
  import { ref } from 'vue';

  const list = ref([1, 2, 3])

  const handleClick = () => {
    list.value.push(list.value.length + 1)
  }

  const isContentShow = ref(false)

  const handleContentShowClick = () => {
    isContentShow.value = !isContentShow.value
  }
</script>

<style scoped>
  ul {
    display: flex;
    gap: 10px;
    max-width: 50%;
    flex-wrap: wrap;
    margin: 0 auto;
  }
  li {
    display: inline-block;
    border: 1px solid #fff;
    border-radius: 4px;
    width: 50px;
    height: 50px;
    line-height: 50px;
    text-align: center;
  }

  button {
    margin-top: 20px;
  }
</style>
<template>
  <div>
    <h1>SWA-GAME</h1>
  </div>
</template>
<script setup lang="js">
  useHead({
    title: 'Game',
    meta: [
      { name: 'description', content: 'My amazing site. With amazing game.' }
    ],
    script: [ { innerHTML: 'console.log(\'Hello world\')' } ]
  })
</script>
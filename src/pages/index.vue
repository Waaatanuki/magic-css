<script setup lang="ts">
const components = computed(() => {
  const fileList = import.meta.glob<Component>('~/components/No*.vue')
  const componentList: Component[] = []
  Object.values(fileList).forEach((c, i) => {
    componentList[i] = defineAsyncComponent(c)
  })
  return componentList
})
</script>

<template>
  <div m-auto max-w-3xl>
    <div text-start text-3xl>
      Magic CSS
    </div>
    <div mt-4 flex gap-2 p-4>
      <div v-for="comp, idx in components" :key="idx">
        <component :is="comp" />
        <span>{{ idx }}</span>
      </div>
    </div>
  </div>
</template>

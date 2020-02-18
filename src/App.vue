<template>
  <VirtualList :listData="data" :estimatedItemSize="100" v-slot="slotProps">
    <Item :item="slotProps.item" />
  </VirtualList>
</template>

<script>
import VirtualList from './components/VirtualList.vue'
import Item from './components/Item.vue'

import faker from 'faker'

const data = []
const COUNT = 10000

for (let id = 0; id < COUNT; id++) {
  data.push({
    id,
    value: faker.lorem.sentences() // 长文本
  })
}

export default {
  name: 'app',
  data() {
    return {
      data
    }
  },
  components: {
    VirtualList,
    Item
  }
}
</script>

<style lang="scss">
html {
  height: 100%;
}
body {
  height: 100%;
  margin: 0;
  padding: 0 20px;
  background: #f7f7f7;
}
#app {
  height: 100%;
}
</style>

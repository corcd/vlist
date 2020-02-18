<template>
  <VirtualList
    v-if="enable"
    :listData="data"
    :estimatedItemSize="100"
    v-slot="slotProps"
  >
    <Item :item="slotProps.item" />
  </VirtualList>
</template>

<script>
import VirtualList from './components/VirtualList.vue'
import Item from './components/Item.vue'

import faker from 'faker'

const data = []
const COUNT = 1000

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
      data,
      enable: true
    }
  },
  components: {
    VirtualList,
    Item
  },
  mounted() {
    // let index = COUNT
    // const timer = setInterval(() => {
    //   index += 10
    //   const temp = [...this.data]
    //   for (let id = index - 10; id < index; id++) {
    //     temp.push({
    //       id,
    //       value: faker.lorem.sentences()
    //     })
    //   }
    //   this.enable = false
    //   this.data = [...temp]
    //   this.$nextTick(() => {
    //     this.enable = true
    //   })
    // }, 5000)
    // this.$once('hook:beforeDestory', () => {
    //   clearInterval(timer)
    // })
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

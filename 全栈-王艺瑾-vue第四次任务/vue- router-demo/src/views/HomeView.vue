<template>
  <div>
    <h1>我是Home组件</h1>
    <router-link to="#" @click.prevent="showList">展示列表</router-link> |
    <router-link to="#" @click.prevent="showChoice">你的选择</router-link>
    <ul v-if="showListItems">
      <li v-for="(item, index) in listItems" :key="index" @click="selectItem(item)">{{ item }}</li>
    </ul>
    <input v-if="showListItems" v-model="newItem" @keyup.enter="addItem" placeholder="请输入事项">
    <div v-if="selectedItem">你的选择是: {{ selectedItem }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listItems: ['吃饭', '睡觉', '打豆豆'],
      newItem: '',
      selectedItem: null,
      showListItems: false
    }
  },
  methods: {
    showList() {
      this.showListItems = true
    },
    showChoice() {
      this.$router.push({ name: 'Choice', params: { item: this.selectedItem } })
    },
    selectItem(item) {
      this.selectedItem = item
      this.$router.push({ name: 'Choice', params: { item } })
    },
    addItem() {
      if (this.newItem.trim() !== '') {
        this.listItems.push(this.newItem)
        this.newItem = ''
      }
    }
  }
}
</script>
<template>
  <div>
    <div>
      <h3>選択肢</h3>
      <draggable
        v-model="itemsA"
        group="myGroup"
        :sort="false"
        @remove="onRemove"
        @start="drag = false"
        @end="drag = false"
        :options="options"
      >
        <div class="item" v-for="item in itemsA" :key="item.id">
          {{ item.name }}
        </div>
      </draggable>
    </div>
    <div class="mb-5">
      <h3>実行するプログラム</h3>
      <draggable
        v-model="itemsB"
        group="myGroup"
        @start="drag = true"
        @end="drag = false"
        :options="options"
      >
        <div class="item" v-for="item in itemsB" :key="item.id">
          {{ item.name }}
        </div>
      </draggable>
    </div>
    <div class="border border-indigo-600 pb-5">
      <h3>この中にドロップで削除</h3>
      <draggable
        group="myGroup"
        @start="drag = true"
        @end="drag = false"
        :options="options"
      >
        <div class="item" v-for="e in trash" :key="e.id">
        </div>
      </draggable>
    </div>
    <div class="mx-auto text-center my-12">
      <button @click="saveItem" class="bg-green-500 hover:bg-green-400 text-white font-bold py-2 px-4 border-b-4 border-green-700 hover:border-green-500 rounded">
        保存
      </button>
    </div>
  </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  name: 'dnd',

  components: { draggable },

  data() {
    return {
      options: {
        group: 'myGroup',
        animation: 200,
      },
      itemsA: [
        { id: 1, name: '前進' },
        { id: 2, name: '右を見る' },
        { id: 3, name: '左を見る' },
        { id: 4, name: '後進' },
      ],
      itemsB: [],
    }
  },
  mounted() {
    if (!localStorage.getItem("itemsB")) {
      localStorage.setItem("itemsB", JSON.stringify([]));
      this.itemsB = [];
    }
    this.itemsB = JSON.parse(localStorage.getItem("itemsB"))
  },
  methods: {
    onRemove () {
      this.itemsA = [
        { id: 1, name: '前進' },
        { id: 2, name: '右を見る' },
        { id: 3, name: '左を見る' },
        { id: 4, name: '後進' },
      ];
    },
    saveItem () {
      localStorage.setItem("itemsB", JSON.stringify(this.itemsB));
      alert('保存しました');
    },
  },
}
</script>

<style scoped>
.item {
  display: inline-block;
  margin: 10px;
  padding: 10px;
  border: 1px solid #7f7f7f;
  border-radius: 10px;
  background-color: #ffffff;
}
.item:hover {
  cursor: grab;
}
.item:active {
  cursor: grabbing;
}
</style>

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
    <div>
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
        pull: false
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
  methods: {
    onRemove (e) {
      this.itemsA = [
        { id: 1, name: '前進' },
        { id: 2, name: '右を見る' },
        { id: 3, name: '左を見る' },
        { id: 4, name: '後進' },
      ];
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

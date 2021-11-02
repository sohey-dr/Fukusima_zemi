<template>
  <div>
    <div>
      <h3>選択肢</h3>
      <draggable
        v-model="itemsA"
        group="myGroup"
        @remove="onRemove"
        @sort="onSort"
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
      },
      itemsA: [
        { id: 1, name: 'name01' },
        { id: 2, name: 'name02' },
        { id: 3, name: 'name03' },
        { id: 4, name: 'name04' },
        { id: 5, name: 'name05' },
      ],
      itemsB: [
        { id: 6, name: 'name06' },
        { id: 7, name: 'name07' },
        { id: 8, name: 'name08' },
        { id: 9, name: 'name09' },
        { id: 10, name: 'name10' },
      ],
    }
  },
  methods: {
    onRemove: function(e) {
      if (this.itemsA.length === 5) {
        // this.itemsA.push({
        //   id: e.draggedContext.element.id,
        //   name: e.draggedContext.element.name,
        // })
      }
      console.log(itemsA)
      return true
    }
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

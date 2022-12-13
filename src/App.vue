<script>
import { ref } from 'vue'
export default {
  setup() {
    const items = ref([
      { id: 0, word: 'A', list: 1 },
      { id: 1, word: 'this', list: 1 },
      { id: 2, word: 'is', list: 1 },
      { id: 3, word: 'amazing', list: 1 },
      { id: 3, word: 'value', list: 1 },
      { id: 3, word: 'for', list: 1 },
      { id: 4, word: 'money', list: 1 },
      { id: 5, word: 'B', list: 2 },
      { id: 6, word: 'I', list: 2 },
      { id: 7, word: 'think', list: 2 },
      { id: 8, word: 'it', list: 2 },
      { id: 9, word: 'is', list: 2 },
      { id: 10, word: 'a', list: 2 },
      { id: 11, word: 'good', list: 2 },
      { id: 12, word: 'product', list: 2 },
      { id: 13, word: 'C', list: 3 },
      { id: 14, word: 'I', list: 3 },
      { id: 15, word: 'am', list: 3 },
      { id: 16, word: 'not', list: 3 },
      { id: 17, word: 'satisfied', list: 3 },
      { id: 18, word: 'with', list: 3 },
      { id: 19, word: 'the', list: 3 },
      { id: 20, word: 'product', list: 3 },
      { id: 21, word: 'D', list: 4 },
      { id: 22, word: 'I', list: 4 },
      { id: 23, word: 'am', list: 4 },
      { id: 24, word: 'very', list: 4 },
      { id: 25, word: 'satisfied', list: 4 },
      { id: 26, word: 'with', list: 4 },
      { id: 27, word: 'the', list: 4 },
      { id: 28, word: 'service', list: 4 },
      { id: 29, word: 'E', list: 5 },
      { id: 30, word: 'I', list: 5 },
      { id: 31, word: 'am', list: 5 },
      { id: 32, word: 'very', list: 5 },
      { id: 33, word: 'satisfied', list: 5 },
      { id: 34, word: 'with', list: 5 },
      { id: 35, word: 'the', list: 5 },
      { id: 36, word: 'product', list: 5 },
    ])

    const getList = (list) => {
      return items.value.filter((item) => item.list === list)
    }

    const startDrag = (event, item) => {
      console.log(item)
      event.dataTransfer.setData('itemID', item.id)
      event.dataTransfer.effectAllowed = 'move'
      event.dataTransfer.dropEffect = 'move'
    }

    const onDrop = (event, list) => {
      event.preventDefault()
      const itemID = event.dataTransfer.getData('itemID')
      const item = items.value.find((item) => item.id === parseInt(itemID))
      item.list = list
    }

    return {
      getList,
      startDrag,
      onDrop
    }
  }
}
</script>

<template class="app">
  <header style="padding: 20px">
    <h1>Step 2: Identifying noun phrases</h1>
    <p>To identify noun phrases, drag words from the scenario description sentences and drop them into the noun phrase
      boxes. Some boxes take multiple words.</p>
  </header>
  <div class="flex-horizontal">
    <div class="drop-zone-horizontal" @drop="onDrop($event, 6)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(6)" :key="item.id" class="drag-el-horizontal" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
        </div>
    </div>
    <div class="drop-zone-horizontal" @drop="onDrop($event, 7)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(7)" :key="item.id" class="drag-el-horizontal" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
        </div>
    </div>
    <div class="drop-zone-horizontal" @drop="onDrop($event, 8)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(8)" :key="item.id" class="drag-el-horizontal" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
        </div>
    </div>
    <div class="drop-zone-horizontal" @drop="onDrop($event, 9)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(9)" :key="item.id" class="drag-el-horizontal" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
        </div>
    </div>
  </div>
  <main class="flexbox">
   
    <div class="drop-zone" @drop="onDrop($event, 1)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(1)" :key="item.id" class="drag-el" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
      </div>
    </div>
    <div class="drop-zone" @drop="onDrop($event, 2)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(2)" :key="item.id" class="drag-el" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
      </div>
    </div>
    <div class="drop-zone" @drop="onDrop($event, 3)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(3)" :key="item.id" class="drag-el" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
      </div>
    </div>
    <div class="drop-zone" @drop="onDrop($event, 4)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(4)" :key="item.id" class="drag-el" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
      </div>
    </div>
    <div class="drop-zone" @drop="onDrop($event, 5)" @dragenter.prevent @dragover.prevent>
      <div v-for="item in getList(5)" :key="item.id" class="drag-el" draggable="true"
        @dragstart="startDrag($event, item)">
        <p>{{ item.word }}</p>
      </div>
    </div>
  </main>
  <footer>
    <div id="buttons" class="relative">
      <button class="navitem">Back</button>
      <button class="navitem">Next</button>
    </div>
  </footer>
</template>

<style scoped>
.drop-zone {
  width: 50%;
  margin: 25px;
  background-color: #ecf0f1;
  height: 90%;
  min-height: 70vh;
  flex-wrap: wrap;
  flex-direction: row;
  padding: 10px;
}

.flex-horizontal{
  display: flex;
  flex-direction: row;
}

.drag-el-horizontal {
  padding-left: 5vh;
  padding-right: 5vh;
  padding-top: 2vh;
  padding-bottom: 2vh;
  background-color: aquamarine;
  margin: 10px;
  flex-direction: row;
  max-width: fit-content;
  cursor: pointer;
}

.drop-zone-horizontal {
  width: 90%;
  margin: 25px;
  background-color: #ecf0f1;
  height: 50%;
  min-height: 20vh;
  max-height: 20vh;
  overflow: scroll;
  flex-wrap: wrap;
  flex-direction: row;
  padding: 10px;
}

.drag-el {
  padding: 5px;
  background-color: aquamarine;
  margin: 10px;
  cursor: pointer;
}

.drag-el:nth-last-of-type(1) {
  margin-bottom: 0;

}

.flexbox {
  display: flex;
  justify-content: space-evenly;

  height: 100%;
  width: 100%;

  overflow: hidden;

  margin: 0 10;
  padding: 15px
}

#buttons {
  width: 50px;
  margin: 0;
  text-align: center;
}

.relative {
  padding: 10px;
  position: relative;
  background-color: #fff;
  margin: 10px;
}

.navitem {
  display: inline-block;
  width: 100px;
  height: 100px;
  text-align: center;
  border: gray;
  background-color: #E8562A;
  color: #fff;
  cursor: pointer;
  font-weight: bold;
}

.navitem:hover {
  background-color: #fff;
  color: #E8562A;
  cursor: pointer;
  font-weight: bold;
}
</style>

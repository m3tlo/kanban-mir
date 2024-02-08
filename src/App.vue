<template>
  <div id="app">
    <KanbanCol
      :col="col"
      :title="col.title"
      :key="col.id"
      v-for="col in columns"
    />
  </div>
</template>

<script>
import KanbanCol from "./components/KanbanCol.vue";
import { columns } from "@/data";

export default {
  components: {
    KanbanCol,
  },
  data: function () {
    return {
      columns: columns,
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  max-width: 90vw;
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  gap: 8px;
  color: #000;
  margin-top: 60px;
}
</style>

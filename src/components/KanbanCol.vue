<template>
  <div class="col">
    <div class="col__title">{{ title }}</div>
    <div class="col__container">
      <div class="col__tasks">
        <KanbanTask
          :description="task.description"
          v-for="task in colTasks"
          :key="task.id"
        />
      </div>
      <button class="col__add-task">add</button>
    </div>
  </div>
</template>

<script>
import KanbanTask from "./KanbanTask.vue";
import { tasks, columns } from "@/data";

export default {
  props: ["title", "col"],
  components: { KanbanTask },
  data: function () {
    return {};
  },
  computed: {
    colTasks() {
      const filteredTasks = tasks.filter((task) => task.parentId === col.id);
      console.log([...columns]);
      return filteredTasks;
    },
  },
};
</script>

<style>
.col {
  display: flex;
  flex-direction: column;
  flex-basis: 20%;
  align-items: center;
}
</style>

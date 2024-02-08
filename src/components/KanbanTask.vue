<template>
  <div class="task">
    <p class="task__description">{{ description }}</p>
    <div class="task__menu"></div>
  </div>
</template>
<script>
export default {
  props: ["description"],
};
</script>

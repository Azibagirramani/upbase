<template>
  <div
    id="CardBase"
    class="card bg-white rounded-card flex-fill shadow-sm"
    :class="custom"
  >
    <div class="card-body">
      <slot></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "CardBase",
  props: {
    custom: {
      type: String,
      default: "",
    },
  },
});
</script>

<style lang="scss" scoped>
.rounded-card {
  border-radius: 1.2rem;
}

.border {
  border: 1px solid #d6d6d8 !important;
}

.card {
  border: none;
}

.card-bg-grey {
  background-color: #f7f6f9 !important;
}

.card-bg-primary {
  background-color: #0525f7 !important;
}
</style>

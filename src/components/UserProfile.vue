<template>
  <div class="d-flex align-items-center gap-2">
    <img src="../assets/profileImage.svg" alt="kristen" class="img-fluid" />
    <div class="d-flex flex-column mt-3 d-none d-lg-block">
      <p class="m-0 p-0 fw-700 fs-1-4 font-gray-darker">Kristen Ramos</p>
      <p class="font-gray fw-600">kristen.ranmos@gmail.com</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({});
</script>

<style lang="scss" scoped>

$gray-color: #6D6E75;

$gray-color-darker: #55565C;

.fs-1-4 {
  font-size: 0.7rem !important;
}
.font-gray-darker {
  color: $gray-color-darker;
}

.font-gray {
  color: $gray-color;
}

.fw-600 {
  font-weight: 600;
}

.fw-700 {
  font-weight: 700;
}

.img-fluid {
  width: 40px;
  height: 30px;
  border-radius: 35%;
}

p {
  font-size: 0.6rem;
  font-weight: 600;
}
</style>

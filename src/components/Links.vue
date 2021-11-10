<template>
  <ul class="nav flex-column" id="Links">
    <li class="nav-item d-flex align-items-center gap-3">
      <i class="fa fa-tachometer"></i>
      <a class="nav-link active d-none d-lg-block" href="#/">Dashboard</a>
    </li>
    <li class="nav-item d-flex align-items-center gap-3">
      <i class="fa fa-tachometer"></i>
      <a class="nav-link d-none d-lg-block" href="#/">Holdings</a>
    </li>
    <li class="nav-item d-flex align-items-center gap-3">
      <i class="fa fa-tachometer"></i>
      <a class="nav-link d-none d-lg-block" href="#/">Performance</a>
    </li>
  </ul>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Links",
});
</script>

<style lang="scss" scoped>
$link-primary: #252533;

.nav-item {
  padding-bottom: 1.3rem;
}

.nav-link {
  color: $link-primary;
  font-size: 0.87rem;
  font-weight: 600;
  text-transform: capitalize;
  transition: all 1s ease-in-out;
  padding-left: 0rem;
}


.nav-link:hover::after {
  content: "";
  display: block;
  border-bottom: red 1px solid;
  width: 1rem;
  height: 0.2rem;
  position: absolute;
}

// i {
//   font-size: 0.8rem;
// }
</style>

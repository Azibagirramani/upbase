<template>
  <div id="SideBar">
    <div class="d-flex flex-column justify-content-lg-between min-vh-100">
      <div class="">
        <UserProfile />
        <div class="mt-5">
          <Links />
        </div>
      </div>

      <div
        class="
          d-flex
          align-items-center
          justify-content-start
          gap-3
          mb-2 mb-lg-
        "
      >
        <i class="fa fa-sign-out" aria-hidden="true"></i>
        <p class="fs-1-1 p-0 m-0 d-none d-lg-block">Logout</p>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import UserProfile from "./UserProfile.vue";
import Links from "./Links.vue";
import { defineComponent } from "vue";
export default defineComponent({
  name: "SideBar",
  components: {
    Links,
    UserProfile,
  },
});
</script>

<style scoped>
.fs-1-1 {
  color: #a4a4b0;
  font-size: 0.7rem;
  font-weight: 700;
}
</style>

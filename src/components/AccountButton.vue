<template>
  <q-btn
    dense
    outline
    rounded
    :class="{
      dark: $q.dark.isActive,
    }"
    class="text-capitalize btn-account justify-center"
  >
    <q-icon name="account_circle" style="color: #085ed4" />
    <span
      v-if="!$q.screen.xs"
      style="color: #085ed4; margin-left: 4px; margin-right: 8px"
    >
      Sign In
    </span>
  </q-btn>
</template>

<style scoped>
.btn-account {
  color: #d3d3d3;
}

.btn-account.dark {
  color: #303030 !important;
}
</style>

<template>
  <q-card flat class="fit">
    <q-card-section>
      <q-input
        v-model="search"
        debounce="500"
        dense
        placeholder="جست و جو کنید"
        borderless
        class="search-input shadow-2 shadow-up-1 q-pa-sm"
      />
    </q-card-section>
  </q-card>
</template>
<script>
export default {
  data() {
    return {
      search: ''
    }
  }
}
</script>
<style lang="scss" scoped>
.search-input {
  // box-shadow: -5px 5px #f7f3f3;
  border-radius: 20px;
}
</style>
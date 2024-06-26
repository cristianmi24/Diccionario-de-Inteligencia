<template>
  <v-card v-if="definition" class="mt-4 pa-4">
    <v-card-title>{{ term }}</v-card-title>
    <v-card-text>{{ definition }}</v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    term: String,
    definition: String,
  },
};
</script>

<style scoped>
.mt-4 {
  margin-top: 1rem;
}
.pa-4 {
  padding: 1rem;
}
</style>

<style scoped>
  .c-subtitle {
    position: relative;
    top: -10px;
  }

  .c-title {
    position: relative;
    top: 5px;
  }

  .rounded-cards {
    border-radius: 2px;
  }

</style>

<!-- This is the card that is spawned for each statistic. -->
<template>
  <v-card v-if="active == kpi.id" width="156" height="140" v-on:click="$emit('update:content')" class="justify-center text-center ma-2 elevation-3 rounded-cards pt-0 mt-0 primary">
    <v-icon size="45" class="pt-5">{{ kpi.icon }}</v-icon>
    <p class="headline c-title">{{ kpi.value }}</p>
    <p class="caption c-subtitle">{{ kpi.name }}</p>
  </v-card>

  <v-card v-else width="156" flat height="140" v-on:click="$emit('update:content')" class="justify-center text-center ma-2 rounded-cards pt-0 mt-0">
    <v-icon size="45" class="pt-5">{{ kpi.icon }}</v-icon>
    <p class="headline c-title">{{ kpi.value }}</p>
    <p class="caption c-subtitle">{{ kpi.name }}</p>
  </v-card>
</template>


<script>
export default{
  computed: {
    active() {
      return this.$store.getters.active
    }
  },
  props:['kpi']
}
</script>

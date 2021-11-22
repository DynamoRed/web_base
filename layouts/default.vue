<template>
  <div>
    <Maintenance v-if="maintenance" />
    <Nuxt v-else/>
  </div>
</template>

<script>
  export default {
    computed: {
      maintenance(){
        return this.$store.state.main.maintenance;
      },
    },
  }
</script>
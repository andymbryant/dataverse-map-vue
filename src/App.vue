<template>
    <InstallationsMap class="installations-map"/>
</template>

<script>
import InstallationsMap from './components/InstallationsMap'

export default {

  name: 'app',
  components: {
    InstallationsMap
  }
}
</script>

<style>
  .installations-map {
    height: 400px;
  }
</style>

<template>
  <div id="app">
    <h3>Starbase Router</h3>
    <h4>
      <router-link to="/data/people" class="link">Meet the Characters</router-link> |
      <router-link to="/data/planets" class="link">Explore the Planets</router-link>
    </h4>
    <router-view></router-view>
  </div>
</template>


<script>
export default {

}
</script>


<style>

</style>


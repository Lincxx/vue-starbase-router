<template>
  <div class="col-md-12">
    <Item
      v-for="(item, index) in items"
      key="item"
      v-bind:item="item"
    />
  </div>
</template>

<script>
import Item from './Item'
export default {
  components: {
    Item
  },
  data(){
    return {
      type: this.$route.params.type,
      items: [],

    }
  },
  methods: {
    fetchItems(){
      this.items = []
      this.type = this.$route.params.type
      let initial_ids = [1, 13, 14]

      for(let i in initial_ids) {
        let id = initial_ids[i]
        //console.log('id', id)
        fetch(`https://swapi.co/api/${this.type}/${id}`, {
          method:'GET'
        }).then(response => response.json())
        .then(json => this.items.push(json))
      }
    }
  },
  watch: {
    '$route': 'fetchItems'
  },
  created() {
    this.fetchItems()
  }
}
</script>


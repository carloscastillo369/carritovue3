<template>
  <div class="container">
    <pre>
      {{carrito}}
    </pre>
    <hr>
    <div class="row">
      <Card
        v-for="producto of productos" :key="producto.id"
        :producto="producto"
      />
    </div>
   
  </div>
</template>

<script>
import Card from "@/components/Card.vue"
import { mapActions, mapState} from "vuex"
export default {
  name: 'Home',
  components: {
    Card
  },

  computed: {
    ...mapState(['productos', 'carrito']),
  },

  methods: {
    ...mapActions(['fetchData'])
  },

  mounted() {
    this.fetchData()
  }
}
</script>
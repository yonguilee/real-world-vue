<template>
  <div>
    <h1>Create an Event, {{ user.name }}</h1>
    <p>This event was created bu {{ user.id }}</p>
    <span>total cat items : {{catLength}}</span>
    <ul>
      <li v-for="cat in categories" :key="cat.id">{{ cat }}</li>
    </ul>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  computed: {
    catLength() {
      return this.$store.getters.catLength
    },
    ...mapState(['user', 'categories'])
  }
}
</script>

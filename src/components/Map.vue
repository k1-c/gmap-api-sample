<template>
  <div class="map">
    <GmapMap
      :center="{lat:10, lng:10}"
      :zoom="7"
      map-type-id="terrain"
      style="width: 100%; height: 500px"
    />
  </div>
</template>

<script lang="ts">
import Vue, { PropOptions } from 'vue'

interface User {
  firstName: string
  lastName: string
}

export default Vue.extend({
  name: 'Map',

  props: {
    user: {
      type: Object,
      required: false
    } as PropOptions<User>
  },

  data () {
    return {
      message: process.env.MAP_API_KEY
    }
  },

  computed: {
    fullName (): string {
      return `${this.user.firstName} ${this.user.lastName}`
    }
  }
})
</script>

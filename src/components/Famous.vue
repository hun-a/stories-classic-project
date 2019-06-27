<template>
  <div id="famous">
    <h2>Trending stories<strong>({{ famous.length }})</strong></h2>
    <ul class="list-group">
      <li v-for="story in famous" :key="story.id" class="list-group-item">
        {{ story.writer }} said "{{ story.plot }}"
        Story upvotes {{ story.upvotes }}.
      </li>
    </ul>
  </div>
</template>

<script>
import { store } from '../store'

export default {
  computed: {
    famous () {
      return store.stories.filter(item => item.upvotes > 50)
    }
  }
}
</script>

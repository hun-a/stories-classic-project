<template>
  <div id="stories">
    <h2>All Stories ({{ stories.length }})</h2>
    <ul class="list-group">
    <li v-for="story in stories" :key="story.id" class="list-group-item">
      <div class="row">
        <h4>
          {{ story.writer }} said "{{ story.plot }}"
          <span class="badge badge-info">Story upvotes {{ story.upvotes }}</span>
        </h4>
        <router-link
          :to="{ name: 'stories.edit', params: { id: story.id } }"
          tag="button"
          class="btn btn-primary"
          exact>
          Edit
        </router-link>
      </div>
    </li>
  </ul>
  </div>
</template>

<script>
import { store } from '../store'

export default {
  data () {
    return {
      stories: store.stories
    }
  },
  mounted () {
    console.log('stories')
  }
}
</script>

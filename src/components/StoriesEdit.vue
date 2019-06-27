<template>
  <dir class="container row">
    <div class="col">
      <h3>Editing</h3>
      <form>
        <div class="form-group">
          <input class="form-control" v-model="story.plot">
        </div>
        <div class="form-group">
          <button @click="saveChanges(story)" class="btn btn-success">
            Save changes
          </button>
        </div>
      </form>
    </div>
  </dir>
</template>

<script>
import { store } from '../store'

export default {
  props: ['id'],
  data () {
    return {
      story: {}
    }
  },
  methods: {
    isTheOne (story) {
      return story.id === this.id
    },
    saveChanges (story) {
      console.log('Saved!')
      this.$router.push('/stories')
    }
  },
  mounted () {
    this.story = store.stories.find(this.isTheOne)
  }
}
</script>

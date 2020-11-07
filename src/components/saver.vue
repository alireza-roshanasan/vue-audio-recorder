<style lang="scss">
  @import '../scss/icons';
</style>

<template>
  <icon-button name="tick" class="ar-icon ar-icon__xs ar-icon--no-border" @click.native="save"/>
</template>

<script>
  import IconButton from './icon-button'
  export default {
    props: {
      record: { type: Object }
    },
    components: {
      IconButton
    },
    methods: {
      save () {
        if (!this.record.url) {
          return
        }
        this.$eventBus.$emit('save-upload', this.record.blob)
      }
    }
  }
</script>

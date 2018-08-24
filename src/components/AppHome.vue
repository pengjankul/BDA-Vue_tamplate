<template>
    <v-container>
       home
    </v-container>
</template>

<script>
  export default {
    data: () => ({
      slider: 56,
      tile: false
    }),

    computed: {
      avatarSize () {
        return `${this.slider}px`
      }
    }
  }
</script>
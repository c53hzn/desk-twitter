<template>
	<div class="desk-unit">
    
  </div>
</template>

<script>
export default {
  props: {
    author: {
      type: String,
      required: true
    },
    id: {
      type: String,
      required: true
    },
    time: {
      type: String,
      required: true
    },
    content: {
      type: Array,
      required: true
    }
  },
}
</script>

<style>

</style>
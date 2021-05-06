<template>
	<div class="desk-unit">
    <div class="content">{{myContent}}</div>
    <div class="share"></div>
  </div>
</template>

<script>
export default {
  data() {
    var myContent = this.content.join("");
    if (myContent.length > 140) {
      myContent = myContent.substring(0,140)+"...";
    }
    return {
      myContent
    }
  },
  props: {
    author: {
      type: [String,null],
      required: true
    },
    id: {
      type: [String,null],
      required: true
    },
    time: {
      type: [String,null],
      required: true
    },
    content: {
      type: [Array,null],
      required: true
    }
  },
}
</script>

<style>
.desk-unit {
  display: flex;
}
.desk-unit .share {
  flex-grow: 1;
}
</style>
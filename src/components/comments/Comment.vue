<template>
  <div class="comment">
    <el-card class="box-card">
      <span style="font-weight:bold">{{ comment.user.email }}:</span>
      <br>
      <span>{{ comment.content }}</span>
    </el-card>
  </div>
</template>

<script>

export default {
  name: 'comment',
  props: {
    comment: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>
  .md-list-item {
    padding-left: 40px;
  }
</style>

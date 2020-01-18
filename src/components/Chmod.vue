<template>
  <div>
    <p>$ chmod <span contenteditable="true" class="num">777</span> foo.md</p>
  </div>
</template>

<script>
export default {
  name: 'Chmod'
}
</script>

<style scoped>
.num {
  font-weight: bold;
  border: 1px solid #ddd;
  padding: 3px;
}

</style>
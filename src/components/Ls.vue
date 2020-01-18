<template>
  <div>
    <p>$ ls -l foo.md</p>
    <p>-{{flags.owner}}{{flags.group}}{{flags.others}} 1 yoda luke 0 2020-01-18 11:42 foo.md</p>
  </div>
</template>

<script>
export default {
  name: 'Ls',
  props: ['flags']
}
</script>

<style scoped>

</style>
<template>
  <div>
    <p>$ chmod 
      <span 
      contenteditable="true" 
      class="num" 
      v-html="bits"
      @input="onInput"
      ></span> foo.md
    </p>
  </div>
</template>

<script>
export default {
  name: 'Chmod',
  data() {
    return {
      bits: '777'
    }
  },
  methods: {
    onInput(e) {
      const bits = e.target.innerHTML;
      if (bits.length === 3) {
        this.bits = e.target.innerHTML;
        this.$emit('bit-change', this.bits);
      }
    }
  }
}
</script>

<style scoped>
.num {
  font-weight: bold;
  border: 1px solid #ddd;
  padding: 3px;
}

</style>
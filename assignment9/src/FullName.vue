<template>
  <div class="form-group">
      <label for="fullname">Full Name:</label>
      <input required type="text" name="fullname" class="form-control" @input="handleInput">
  </div>
</template>

<script>
export default {
  methods: {
    handleInput(e) {
      this.$emit('input', e.target.value)
    }
  }
}
</script>

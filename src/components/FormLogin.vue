<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h2>LOGIN</h2>
      </div>

      <div slot="form-fields">
        <input type="text" placeholder="enter your name ..." />
      </div>

      <div slot="form-controls">
        <button @click="alert('hey!')">submit</button>
      </div>
    </form-helper>
  </div>
</template>

<script>
import FormHelper from '@/components/FormHelper'
    export default {
        name: "FormLogin",
        components: {
          FormHelper
        }
    }
</script>

<style lang="scss" scoped>
</style>
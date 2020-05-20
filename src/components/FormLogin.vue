<template>
  <div>
    <form-helper>
      <div slot="form-header">
        <h2>LOGIN</h2>
      </div>

      <div slot="form-fields">
        <input type="text" placeholder="enter your name ..." />
        <div>
          <label>rice</label>
          <input type="checkbox" value="rice" v-model="categories" />
          <label>chicken</label>
          <input type="checkbox" value="chicken" v-model="categories" />
          <label>ramen</label>
          <input type="checkbox" value="ramen" v-model="categories" />
        </div>
      </div>

      <div slot="form-controls">
        <button @click.prevent="handleFuck">submit</button>
        <div>
          <h3>Preview Form</h3>
          <ul>
            <ol v-for="(category,index) in categories" :key="index">{{category}}</ol>
          </ul>
        </div>
      </div>
    </form-helper>
  </div>
</template>

<script>
import FormHelper from '@/components/FormHelper'
    export default {
        name: "FormLogin",
        data() {
          return {
            categories: []
          } 
        },
        components: {
          FormHelper
        },
        methods: {
          handleFuck() {
            this.$emit('fuck', 'fuck')
          }
        }
    }
</script>

<style lang="scss" scoped>
</style>